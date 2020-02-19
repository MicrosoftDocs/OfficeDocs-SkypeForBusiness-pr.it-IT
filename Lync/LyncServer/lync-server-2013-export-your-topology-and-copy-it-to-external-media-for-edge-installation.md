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
ms.openlocfilehash: 784ed29372b137d5d3f58d749a3660d11cbb55d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a><span data-ttu-id="1405c-102">Esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale</span><span class="sxs-lookup"><span data-stu-id="1405c-102">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1405c-103">_**Ultimo argomento modificato:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1405c-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1405c-104">Dopo aver pubblicato la topologia, la distribuzione guidata di Lync Server deve accedere ai dati dell'archivio di gestione centrale al fine di avviare il processo di distribuzione sul server.</span><span class="sxs-lookup"><span data-stu-id="1405c-104">After you publish your topology, the Lync Server Deployment Wizard needs access to the Central Management store data in order to start the deployment process on the server.</span></span> <span data-ttu-id="1405c-105">Nella rete interna, i dati sono disponibili direttamente dai server, ma i server perimetrali che non sono nel dominio interno non possono accedere ai dati.</span><span class="sxs-lookup"><span data-stu-id="1405c-105">In the internal network, the data is available directly from the servers, but Edge Servers that are not in the internal domain cannot access the data.</span></span> <span data-ttu-id="1405c-106">Per rendere disponibili i dati di configurazione della topologia per una distribuzione di server perimetrali, è necessario esportare i dati della topologia in un file e copiarli in un supporto esterno, ad esempio un'unità USB o una condivisione di rete disponibile dal server perimetrale, prima di eseguire la funzionalità di protezione esecuzione programmi di Lync Server. loyment Wizard sul server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="1405c-106">To make the topology configuration data available for an Edge Server deployment, you must export the topology data to a file and copy it to external media (for example, a USB drive or a network share that is available from the Edge Server) before you run the Lync Server Deployment Wizard on the Edge Server.</span></span> <span data-ttu-id="1405c-107">Utilizzare la procedura seguente per rendere disponibili i dati di configurazione della topologia nel server perimetrale che si sta distribuendo.</span><span class="sxs-lookup"><span data-stu-id="1405c-107">Use the following procedure to make your topology configuration data available on the Edge Server that you are deploying.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="1405c-108">Dopo aver installato Lync Server 2013 in un server perimetrale, è possibile gestire il server perimetrale utilizzando gli strumenti di amministrazione della rete interna, che replicano automaticamente la configurazione in tutti i server perimetrali della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1405c-108">After you install Lync Server 2013 on an Edge Server, you manage the Edge Server using the administrative tools in the internal network, which automatically replicate configuration to any Edge Servers in your deployment.</span></span> <span data-ttu-id="1405c-109">L'unica eccezione è l'assegnazione e l'installazione di certificati e l'arresto e l'avvio dei servizi, che devono essere entrambi eseguiti nel server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="1405c-109">The only exception is assigning and installing certificates and stopping and starting services, both of which must be done on the Edge Server.</span></span>



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a><span data-ttu-id="1405c-110">Per rendere disponibili i dati della topologia in un server perimetrale tramite Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="1405c-110">To make your topology data available on an Edge Server by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="1405c-111">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1405c-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1405c-112">In Lync Server Management Shell, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="1405c-112">In the Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  <span data-ttu-id="1405c-113">Copiare il file esportato in un supporto esterno, ad esempio un'unità USB o una condivisione di rete disponibile dal server perimetrale durante la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1405c-113">Copy the exported file to external media (for example, a USB drive or a network share that is available from the Edge Server during deployment).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

