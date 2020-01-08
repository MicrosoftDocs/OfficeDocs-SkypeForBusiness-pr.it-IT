---
title: 'Lync Server 2013: Selezionare il server di gestione centrale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Select the Central Management Server
ms:assetid: 1ca6b7d0-125c-4727-aac4-2d683d23394d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204726(v=OCS.15)
ms:contentKeyID: 48183561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: daa99142b1e0814335ea1ca1de8ecf5452029943
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="select-the-central-management-server-in-lync-server-2013"></a><span data-ttu-id="451b6-102">Selezionare il server di gestione centrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="451b6-102">Select the Central Management Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="451b6-103">_**Argomento Ultima modifica:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="451b6-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="451b6-104">Prima di poter definire e configurare la topologia, è prima di tutto necessario definire la posizione in cui installare il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="451b6-104">Before you can define and configure your topology, you must first define the location to install the Central Management Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="451b6-105">Questa operazione non avrà effetto finché non verrà pubblicata una topologia in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="451b6-105">This will not take effect until you have published a topology in Topology Builder.</span></span> <span data-ttu-id="451b6-106">Per impostare il server di gestione centralizzato prima della creazione e della pubblicazione della topologia, eseguire <STRONG>set-CSConfigurationStoreLocation</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="451b6-106">To set the Central Management Server before the topology is created and published, run <STRONG>Set-CSConfigurationStoreLocation</STRONG>.</span></span>



</div>

<div>

## <a name="to-select-the-central-management-server"></a><span data-ttu-id="451b6-107">Per selezionare il server di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="451b6-107">To select the Central Management Server</span></span>

1.  <span data-ttu-id="451b6-108">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="451b6-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="451b6-109">Fare clic con il pulsante destro del mouse sul nodo Lync Server 2013 e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="451b6-109">Right-click the Lync Server 2013 node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="451b6-110">Nel riquadro Central Management Server selezionare il server front-end per installare il server di gestione centrale e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="451b6-110">In the Central Management Server pane, select the Front End Server to install the Central Management Server on and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

