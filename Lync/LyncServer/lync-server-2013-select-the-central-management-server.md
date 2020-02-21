---
title: 'Lync Server 2013: selezionare il server di gestione centrale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Select the Central Management Server
ms:assetid: 1ca6b7d0-125c-4727-aac4-2d683d23394d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204726(v=OCS.15)
ms:contentKeyID: 48183561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1345a26cd7535fbeccf34c822496051d2dd97a9e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="select-the-central-management-server-in-lync-server-2013"></a><span data-ttu-id="30d66-102">Selezionare il server di gestione centrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30d66-102">Select the Central Management Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30d66-103">_**Ultimo argomento modificato:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="30d66-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="30d66-104">Prima di poter definire e configurare la topologia, è innanzitutto necessario definire il percorso in cui installare il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="30d66-104">Before you can define and configure your topology, you must first define the location to install the Central Management Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="30d66-105">Questo non avrà effetto finché non verrà pubblicata una topologia in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="30d66-105">This will not take effect until you have published a topology in Topology Builder.</span></span> <span data-ttu-id="30d66-106">Per impostare il server di gestione centrale prima della creazione e della pubblicazione della topologia, eseguire <STRONG>set-CSConfigurationStoreLocation</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="30d66-106">To set the Central Management Server before the topology is created and published, run <STRONG>Set-CSConfigurationStoreLocation</STRONG>.</span></span>



</div>

<div>

## <a name="to-select-the-central-management-server"></a><span data-ttu-id="30d66-107">Per selezionare il server di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="30d66-107">To select the Central Management Server</span></span>

1.  <span data-ttu-id="30d66-108">Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.</span><span class="sxs-lookup"><span data-stu-id="30d66-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="30d66-109">Fare clic con il pulsante destro del mouse sul nodo Lync Server 2013 e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="30d66-109">Right-click the Lync Server 2013 node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="30d66-110">Nel riquadro del server di gestione centrale, selezionare il front end server per installare il server di gestione centrale e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="30d66-110">In the Central Management Server pane, select the Front End Server to install the Central Management Server on and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

