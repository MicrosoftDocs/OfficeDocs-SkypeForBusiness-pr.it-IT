---
title: 'Lync Server 2013: Pubblicare la topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bd542db6acedbec75e475045ae2ace6d63d5469
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-your-topology-in-lync-server-2013"></a><span data-ttu-id="ffc16-102">Pubblicare la topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffc16-102">Publish your topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffc16-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="ffc16-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="ffc16-104">Ogni volta che si usa generatore di topologie per compilare la topologia, è necessario pubblicare la topologia in un database in Central Management store in modo che i dati possano essere usati per distribuire Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ffc16-104">Each time you use Topology Builder to build your topology, you must publish the topology to a database in the Central Management store so that the data can be used to deploy Lync Server 2013.</span></span> <span data-ttu-id="ffc16-105">Usare la procedura seguente per pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="ffc16-105">Use the following procedure to publish your topology.</span></span>

<div>

## <a name="to-publish-the-topology"></a><span data-ttu-id="ffc16-106">Per pubblicare la topologia</span><span class="sxs-lookup"><span data-stu-id="ffc16-106">To publish the topology</span></span>

1.  <span data-ttu-id="ffc16-107">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ffc16-107">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="ffc16-108">Nell'albero della console, in Generatore di topologia, fare clic con il pulsante destro del mouse su **Lync 2013**e quindi scegliere **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="ffc16-108">In Topology Builder, in the console tree, right-click **Lync 2013**, and then click **Publish Topology**.</span></span>

3.  <span data-ttu-id="ffc16-109">Nella pagina di **benvenuto** della procedura guidata fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ffc16-109">On the **Welcome** page of the wizard, click **Next**.</span></span>

4.  <span data-ttu-id="ffc16-110">Nella pagina **Generatore di topologia è stata trovata una pagina di CMS Store** , fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ffc16-110">On the **Topology Builder found a CMS store** page, click **Next**.</span></span>

5.  <span data-ttu-id="ffc16-111">Nella pagina **crea altri database** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="ffc16-111">On the **Create other databases** page, click **Next**.</span></span>

6.  <span data-ttu-id="ffc16-112">Quando lo stato indica che la creazione del database è riuscita, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ffc16-112">When the status indicates that database creation succeeded, do the following:</span></span>
    
      - <span data-ttu-id="ffc16-113">Per visualizzare il log, fare clic su **Visualizza log**.</span><span class="sxs-lookup"><span data-stu-id="ffc16-113">To view the log, click **View log**.</span></span>
    
      - <span data-ttu-id="ffc16-114">Per chiudere la procedura guidata, fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="ffc16-114">To close the wizard, click **Finish**.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="ffc16-115">Se si tratta di una nuova installazione di un server perimetrale o di un pool di Edge, è necessario esportare la configurazione del server perimetrale da un server front-end esistente, un pool Front-end o un server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="ffc16-115">If this is a new installation of an Edge Server or Edge pool, you must export the Edge Server configuration from an existing Front End Server, Front End pool, or Standard Edition server.</span></span> <span data-ttu-id="ffc16-116">Per esportare la configurazione, vedere <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">esportare la topologia di Lync Server 2013 e copiarla in elementi multimediali esterni per l'installazione di Edge</A>.</span><span class="sxs-lookup"><span data-stu-id="ffc16-116">To export the configuration, see <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A>.</span></span> <span data-ttu-id="ffc16-117">Il file di configurazione verrà importato dal supporto esterno o dalla condivisione di rete durante la fase di configurazione e distribuzione degli Edge Server tramite la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ffc16-117">You will import the configuration file from the external media or network share during the setup and deployment phase of the Edge Servers through the Lync Server Deployment Wizard.</span></span><BR><span data-ttu-id="ffc16-118">Una volta che i server perimetrali sono operativi e il database dell'archivio di gestione della configurazione locale viene replicato con la distribuzione interna, gli aggiornamenti successivi alla configurazione di Lync Server 2013 verranno pubblicati e replicati in Edge Server.</span><span class="sxs-lookup"><span data-stu-id="ffc16-118">Once the Edge Servers are operational and the local configuration management store database is replicating with the internal deployment, subsequent updates to the Lync Server 2013 configuration will be published and replicated to the Edge Servers.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

