---
title: 'Lync Server 2013: definizione e configurazione della topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining and configuring the topology
ms:assetid: 51d1601e-4f83-48d4-ad08-3b4d5e2003aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398339(v=OCS.15)
ms:contentKeyID: 48184146
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4f4f5ef6dfe595c87745571d061d104916067c8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-and-configuring-the-topology-in-lync-server-2013"></a><span data-ttu-id="fbb77-102">Definizione e configurazione della topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbb77-102">Defining and configuring the topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbb77-103">_**Ultimo argomento modificato:** 2012-09-14_</span><span class="sxs-lookup"><span data-stu-id="fbb77-103">_**Topic Last Modified:** 2012-09-14_</span></span>

<span data-ttu-id="fbb77-104">È possibile definire e configurare la topologia tramite Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="fbb77-104">You define and configure your topology by using Topology Builder.</span></span> <span data-ttu-id="fbb77-105">In Generatore di topologie non è necessario essere membri del gruppo Administrators locale o di un gruppo di dominio con privilegi, ad esempio Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="fbb77-105">Topology Builder does not require you to be a member of the local Administrators group or a privileged domain group (such as Domain Admins).</span></span> <span data-ttu-id="fbb77-106">È possibile definire la topologia come utenti standard.</span><span class="sxs-lookup"><span data-stu-id="fbb77-106">You can define your topology as a standard user.</span></span> <span data-ttu-id="fbb77-107">All'avvio di Generatore di topologie per il primo utilizzo e le sessioni di modifica successive viene richiesto di specificare la posizione in cui deve essere caricato il documento della configurazione corrente.</span><span class="sxs-lookup"><span data-stu-id="fbb77-107">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="fbb77-108">Le scelte disponibili sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbb77-108">The choices are the following:</span></span>

  - <span data-ttu-id="fbb77-109">Scarica topologia dalla distribuzione esistente</span><span class="sxs-lookup"><span data-stu-id="fbb77-109">Download topology from existing deployment</span></span>

  - <span data-ttu-id="fbb77-110">Apri topologia da un file locale</span><span class="sxs-lookup"><span data-stu-id="fbb77-110">Open topology from a local file</span></span>

  - <span data-ttu-id="fbb77-111">Nuova topologia</span><span class="sxs-lookup"><span data-stu-id="fbb77-111">New topology</span></span>

<span data-ttu-id="fbb77-112">Se è già stata definita una topologia e l'archivio di gestione centrale è stato definito, è consigliabile scegliere di scaricare una topologia da una distribuzione esistente.</span><span class="sxs-lookup"><span data-stu-id="fbb77-112">If you have already defined a topology and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="fbb77-113">Generatore di topologie leggerà il database e recupererà la definizione corrente.</span><span class="sxs-lookup"><span data-stu-id="fbb77-113">Topology Builder will read the database and retrieve the current definition.</span></span> <span data-ttu-id="fbb77-114">Se si dispone di un archivio di gestione centrale esistente, è sempre necessario scegliere questa opzione.</span><span class="sxs-lookup"><span data-stu-id="fbb77-114">If you have an existing Central Management store, you should always choose this option.</span></span>

<span data-ttu-id="fbb77-115">Se non è stato stabilito un archivio di gestione centrale e si desidera modificare una configurazione salvata in precedenza, è necessario scegliere di aprire la topologia da un file locale.</span><span class="sxs-lookup"><span data-stu-id="fbb77-115">If you have not established a Central Management store and want to edit a previously saved configuration, you should choose to open the topology from a local file.</span></span> <span data-ttu-id="fbb77-116">Il file che verrà aperto sarà il file di configurazione salvato in una sessione precedente.</span><span class="sxs-lookup"><span data-stu-id="fbb77-116">The file that you will open would be the configuration file that was saved in a previous session.</span></span> <span data-ttu-id="fbb77-117">È possibile utilizzare questa opzione per modificare la topologia salvata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="fbb77-117">You can use this option to edit the previously saved topology.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="fbb77-p104">Se è già disponibile una topologia pubblicata, è sconsigliabile caricare un file di configurazione locale, ma è preferibile scegliere di scaricare la topologia da una distribuzione esistente.</span><span class="sxs-lookup"><span data-stu-id="fbb77-p104">If you already have a published topology, you should not load a local configuration file. You should choose to download the topology from an existing deployment.</span></span>



</div>

<span data-ttu-id="fbb77-120">Scegliere di creare una nuova topologia, se si desidera creare una nuova configurazione del generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="fbb77-120">Choose to create a new topology, if you want to create a new Topology Builder configuration.</span></span> <span data-ttu-id="fbb77-121">Una progettazione salvata in precedenza non viene sovrascritta a meno che non si scelga di salvarla nello stesso file creato in una sessione di progettazione precedente.</span><span class="sxs-lookup"><span data-stu-id="fbb77-121">A previously saved design is not overwritten unless you choose to save it as the same file that you created in an earlier design session.</span></span>

<span data-ttu-id="fbb77-122">In ognuna di queste opzioni verrà richiesto un percorso in cui archiviare il file di configurazione del generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="fbb77-122">In each of these options, you will be prompted for a location to store the Topology Builder configuration file.</span></span> <span data-ttu-id="fbb77-123">Il percorso per il file può essere locale, condiviso in una condivisione file specifica oppure su un supporto rimovibile.</span><span class="sxs-lookup"><span data-stu-id="fbb77-123">The location for the file could be a local location, a shared location on an established file share, or removable media.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fbb77-124">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="fbb77-124">In This Section</span></span>

  - [<span data-ttu-id="fbb77-125">Definire e configurare una topologia in Generatore di topologie per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbb77-125">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md)

  - [<span data-ttu-id="fbb77-126">Definire e configurare un pool Front end o un server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbb77-126">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)

  - [<span data-ttu-id="fbb77-127">Distribuzione di pool Front End abbinati per il ripristino di emergenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbb77-127">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>](lync-server-2013-deploying-paired-front-end-pools-for-disaster-recovery.md)

  - [<span data-ttu-id="fbb77-128">Distribuzione del mirroring di SQL per la disponibilità elevata del server back-end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbb77-128">Deploying SQL mirroring for Back End Server high availability in Lync Server 2013</span></span>](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

  - [<span data-ttu-id="fbb77-129">Modificare o configurare URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbb77-129">Edit or configure simple URLs in Lync Server 2013</span></span>](lync-server-2013-edit-or-configure-simple-urls.md)

  - [<span data-ttu-id="fbb77-130">Selezionare il server di gestione centrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbb77-130">Select the Central Management Server in Lync Server 2013</span></span>](lync-server-2013-select-the-central-management-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

