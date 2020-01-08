---
title: 'Lync Server 2013: Definizione e configurazione della topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8660ac75e325e5737ceb5df59e9463c88ef1c077
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a><span data-ttu-id="e4186-102">Definizione e configurazione della topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4186-102">Defining and configuring the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4186-103">_**Argomento Ultima modifica:** 2012-09-14_</span><span class="sxs-lookup"><span data-stu-id="e4186-103">_**Topic Last Modified:** 2012-09-14_</span></span>

<span data-ttu-id="e4186-104">Puoi definire e configurare la topologia usando generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="e4186-104">You define and configure your topology by using Topology Builder.</span></span> <span data-ttu-id="e4186-105">Generatore di topologie non richiede di essere un membro del gruppo Administrators locale o di un gruppo di domini privilegiati, ad esempio Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="e4186-105">Topology Builder does not require you to be a member of the local Administrators group or a privileged domain group (such as Domain Admins).</span></span> <span data-ttu-id="e4186-106">Puoi definire la topologia come utente standard.</span><span class="sxs-lookup"><span data-stu-id="e4186-106">You can define your topology as a standard user.</span></span> <span data-ttu-id="e4186-107">Quando si avvia il generatore di topologia al primo utilizzo e alle successive sessioni di modifica, viene richiesto il percorso in cui si vuole che il generatore di topologia carichi il documento di configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="e4186-107">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="e4186-108">Le opzioni disponibili sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4186-108">The choices are the following:</span></span>

  - <span data-ttu-id="e4186-109">Scarica topologia dalla distribuzione esistente</span><span class="sxs-lookup"><span data-stu-id="e4186-109">Download topology from existing deployment</span></span>

  - <span data-ttu-id="e4186-110">Aprire la topologia da un file locale</span><span class="sxs-lookup"><span data-stu-id="e4186-110">Open topology from a local file</span></span>

  - <span data-ttu-id="e4186-111">Nuova topologia</span><span class="sxs-lookup"><span data-stu-id="e4186-111">New topology</span></span>

<span data-ttu-id="e4186-112">Se è già stata definita una topologia e si è stabilita l'Central Management store, è consigliabile scegliere di scaricare una topologia da una distribuzione esistente.</span><span class="sxs-lookup"><span data-stu-id="e4186-112">If you have already defined a topology and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="e4186-113">Generatore di topologia leggerà il database e recupererà la definizione corrente.</span><span class="sxs-lookup"><span data-stu-id="e4186-113">Topology Builder will read the database and retrieve the current definition.</span></span> <span data-ttu-id="e4186-114">Se si ha un Central Management store esistente, è sempre consigliabile scegliere questa opzione.</span><span class="sxs-lookup"><span data-stu-id="e4186-114">If you have an existing Central Management store, you should always choose this option.</span></span>

<span data-ttu-id="e4186-115">Se non è stato stabilito un Central Management store e si vuole modificare una configurazione salvata in precedenza, è consigliabile scegliere di aprire la topologia da un file locale.</span><span class="sxs-lookup"><span data-stu-id="e4186-115">If you have not established a Central Management store and want to edit a previously saved configuration, you should choose to open the topology from a local file.</span></span> <span data-ttu-id="e4186-116">Il file che verrà aperto sarà il file di configurazione salvato in una sessione precedente.</span><span class="sxs-lookup"><span data-stu-id="e4186-116">The file that you will open would be the configuration file that was saved in a previous session.</span></span> <span data-ttu-id="e4186-117">Puoi usare questa opzione per modificare la topologia salvata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="e4186-117">You can use this option to edit the previously saved topology.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="e4186-118">Se si dispone già di una topologia pubblicata, non è necessario caricare un file di configurazione locale.</span><span class="sxs-lookup"><span data-stu-id="e4186-118">If you already have a published topology, you should not load a local configuration file.</span></span> <span data-ttu-id="e4186-119">È consigliabile scegliere di scaricare la topologia da una distribuzione esistente.</span><span class="sxs-lookup"><span data-stu-id="e4186-119">You should choose to download the topology from an existing deployment.</span></span>



</div>

<span data-ttu-id="e4186-120">Scegliere per creare una nuova topologia, se si vuole creare una nuova configurazione di generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="e4186-120">Choose to create a new topology, if you want to create a new Topology Builder configuration.</span></span> <span data-ttu-id="e4186-121">Una struttura salvata in precedenza non viene sovrascritta a meno che non si scelga di salvarla come lo stesso file creato in una sessione di progettazione precedente.</span><span class="sxs-lookup"><span data-stu-id="e4186-121">A previously saved design is not overwritten unless you choose to save it as the same file that you created in an earlier design session.</span></span>

<span data-ttu-id="e4186-122">In ognuna di queste opzioni verrà richiesto un percorso in cui archiviare il file di configurazione del generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="e4186-122">In each of these options, you will be prompted for a location to store the Topology Builder configuration file.</span></span> <span data-ttu-id="e4186-123">La posizione del file può essere una posizione locale, una posizione condivisa in una condivisione file stabilita o un elemento multimediale rimovibile.</span><span class="sxs-lookup"><span data-stu-id="e4186-123">The location for the file could be a local location, a shared location on an established file share, or removable media.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e4186-124">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e4186-124">In This Section</span></span>

  - [<span data-ttu-id="e4186-125">Definire e configurare una topologia in Generatore di topologie per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4186-125">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [<span data-ttu-id="e4186-126">Definire e configurare un pool Front End o un server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4186-126">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="e4186-127">Distribuzione di pool Front End abbinati per il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4186-127">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [<span data-ttu-id="e4186-128">Distribuzione del mirroring di SQL per la disponibilità elevata del server back-end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4186-128">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [<span data-ttu-id="e4186-129">Modificare o configurare URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4186-129">Edit or configure simple URLs in Lync Server 2013</span></span>](lync-server-2013-edit-or-configure-simple-urls.md)

  - [<span data-ttu-id="e4186-130">Selezionare il server di gestione centrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4186-130">Select the Central Management Server in Lync Server 2013</span></span>](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

