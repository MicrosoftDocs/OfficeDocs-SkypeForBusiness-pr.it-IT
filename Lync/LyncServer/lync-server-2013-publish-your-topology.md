---
title: 'Lync Server 2013: pubblicare la topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 591942ae8b3df74e14e254e984cd322239c4d7e6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-your-topology-in-lync-server-2013"></a><span data-ttu-id="c9ab6-102">Pubblicare la topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9ab6-102">Publish your topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9ab6-103">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="c9ab6-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="c9ab6-104">Ogni volta che si utilizza il generatore di topologie per creare la topologia, è necessario pubblicare la topologia in un database nell'archivio di gestione centrale in modo che i dati possano essere utilizzati per la distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c9ab6-104">Each time you use Topology Builder to build your topology, you must publish the topology to a database in the Central Management store so that the data can be used to deploy Lync Server 2013.</span></span> <span data-ttu-id="c9ab6-105">Eseguire la procedura seguente per pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="c9ab6-105">Use the following procedure to publish your topology.</span></span>

<div>

## <a name="to-publish-the-topology"></a><span data-ttu-id="c9ab6-106">Per pubblicare la topologia</span><span class="sxs-lookup"><span data-stu-id="c9ab6-106">To publish the topology</span></span>

1.  <span data-ttu-id="c9ab6-107">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="c9ab6-107">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="c9ab6-108">In Generatore di topologie, nell'albero della console, fare clic con il pulsante destro del mouse su **Lync 2013**e quindi scegliere **Pubblica topologia**.</span><span class="sxs-lookup"><span data-stu-id="c9ab6-108">In Topology Builder, in the console tree, right-click **Lync 2013**, and then click **Publish Topology**.</span></span>

3.  <span data-ttu-id="c9ab6-109">Nella pagina iniziale della\*\*\*\* procedura guidata fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c9ab6-109">On the **Welcome** page of the wizard, click **Next**.</span></span>

4.  <span data-ttu-id="c9ab6-110">Nella pagina **Archivio di gestione centrale rilevato da Generatore di topologie** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c9ab6-110">On the **Topology Builder found a CMS store** page, click **Next**.</span></span>

5.  <span data-ttu-id="c9ab6-111">Nella pagina **Crea database** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c9ab6-111">On the **Create other databases** page, click **Next**.</span></span>

6.  <span data-ttu-id="c9ab6-112">Quando lo stato indica che la creazione del database è stata completata, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9ab6-112">When the status indicates that database creation succeeded, do the following:</span></span>
    
      - <span data-ttu-id="c9ab6-113">Per visualizzare il registro, fare clic su **Visualizza registro**.</span><span class="sxs-lookup"><span data-stu-id="c9ab6-113">To view the log, click **View log**.</span></span>
    
      - <span data-ttu-id="c9ab6-114">Per chiudere la procedura guidata, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="c9ab6-114">To close the wizard, click **Finish**.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="c9ab6-115">Se si tratta di una nuova installazione di un server perimetrale o di un pool di Edge, è necessario esportare la configurazione del server perimetrale da un server front end server esistente, un pool Front end o uno Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="c9ab6-115">If this is a new installation of an Edge Server or Edge pool, you must export the Edge Server configuration from an existing Front End Server, Front End pool, or Standard Edition server.</span></span> <span data-ttu-id="c9ab6-116">Per esportare la configurazione, vedere <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale</A>.</span><span class="sxs-lookup"><span data-stu-id="c9ab6-116">To export the configuration, see <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A>.</span></span> <span data-ttu-id="c9ab6-117">Il file di configurazione verrà importato dal supporto esterno o dalla condivisione di rete durante la fase di installazione e distribuzione dei server perimetrali tramite la distribuzione guidata di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c9ab6-117">You will import the configuration file from the external media or network share during the setup and deployment phase of the Edge Servers through the Lync Server Deployment Wizard.</span></span><BR><span data-ttu-id="c9ab6-118">Una volta che i server perimetrali sono operativi e il database dell'archivio di gestione della configurazione locale viene replicato con la distribuzione interna, i successivi aggiornamenti alla configurazione di Lync Server 2013 verranno pubblicati e replicati nei server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="c9ab6-118">Once the Edge Servers are operational and the local configuration management store database is replicating with the internal deployment, subsequent updates to the Lync Server 2013 configuration will be published and replicated to the Edge Servers.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

