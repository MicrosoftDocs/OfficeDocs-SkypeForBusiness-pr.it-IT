---
title: Esportare la topologia e copiarla su supporto esterno per l'installazione perimetrale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb8f20e7af8cbfd772226917b027a33a688a4a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a><span data-ttu-id="2789b-102">Esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale</span><span class="sxs-lookup"><span data-stu-id="2789b-102">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2789b-103">_**Argomento Ultima modifica:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="2789b-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="2789b-104">Dopo aver pubblicato la topologia, la distribuzione guidata di Lync Server deve accedere ai dati di Central Management store per avviare il processo di distribuzione nel server.</span><span class="sxs-lookup"><span data-stu-id="2789b-104">After you publish your topology, the Lync Server Deployment Wizard needs access to the Central Management store data in order to start the deployment process on the server.</span></span> <span data-ttu-id="2789b-105">Nella rete interna i dati sono disponibili direttamente dai server, ma i server perimetrali non inclusi nel dominio interno non possono accedere ai dati.</span><span class="sxs-lookup"><span data-stu-id="2789b-105">In the internal network, the data is available directly from the servers, but Edge Servers that are not in the internal domain cannot access the data.</span></span> <span data-ttu-id="2789b-106">Per rendere disponibili i dati di configurazione della topologia per una distribuzione di Edge Server, è necessario esportare i dati della topologia in un file e copiarli in elementi multimediali esterni, ad esempio un'unità USB o una condivisione di rete disponibile dall'Edge Server, prima di eseguire la protezione esecuzione programmi di Lync Server loyment guidata nel server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="2789b-106">To make the topology configuration data available for an Edge Server deployment, you must export the topology data to a file and copy it to external media (for example, a USB drive or a network share that is available from the Edge Server) before you run the Lync Server Deployment Wizard on the Edge Server.</span></span> <span data-ttu-id="2789b-107">Usare la procedura seguente per rendere disponibili i dati di configurazione della topologia nell'Edge Server che si sta distribuendo.</span><span class="sxs-lookup"><span data-stu-id="2789b-107">Use the following procedure to make your topology configuration data available on the Edge Server that you are deploying.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="2789b-108">Dopo l'installazione di Lync Server 2013 in un server perimetrale, è possibile gestire il server perimetrale usando gli strumenti di amministrazione della rete interna, che riproducono automaticamente la configurazione in qualsiasi server perimetrale della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2789b-108">After you install Lync Server 2013 on an Edge Server, you manage the Edge Server using the administrative tools in the internal network, which automatically replicate configuration to any Edge Servers in your deployment.</span></span> <span data-ttu-id="2789b-109">L'unica eccezione è l'assegnazione e l'installazione di certificati e l'arresto e l'avvio dei servizi, che devono essere eseguiti nel server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="2789b-109">The only exception is assigning and installing certificates and stopping and starting services, both of which must be done on the Edge Server.</span></span>



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a><span data-ttu-id="2789b-110">Per rendere disponibili i dati della topologia in un server perimetrale tramite Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="2789b-110">To make your topology data available on an Edge Server by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="2789b-111">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="2789b-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2789b-112">In Lync Server Management Shell eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="2789b-112">In the Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  <span data-ttu-id="2789b-113">Copiare il file esportato in elementi multimediali esterni, ad esempio un'unità USB o una condivisione di rete disponibile dall'Edge Server durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2789b-113">Copy the exported file to external media (for example, a USB drive or a network share that is available from the Edge Server during deployment).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

