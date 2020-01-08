---
title: 'Lync Server 2013: configurazione dei computer Lync Server che verranno monitorati'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the Lync Server computers that will be monitored
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48184927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a5d252035820f373183d1927b322a929340716
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a><span data-ttu-id="0da50-102">Configurazione dei computer Lync Server che verranno monitorati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0da50-102">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0da50-103">_**Argomento Ultima modifica:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="0da50-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="0da50-104">Poiché Lync Server 2013 non usa il processo di individuazione centralizzato usato in Microsoft Lync Server 2010, ogni computer Lync Server 2013 che si vuole monitorare deve essere in grado di auto-segnalare la propria esistenza al server di gestione.</span><span class="sxs-lookup"><span data-stu-id="0da50-104">Because Lync Server 2013 does not use the central discovery process used in Microsoft Lync Server 2010, each Lync Server 2013 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="0da50-105">Per rendere possibile questo problema, è necessario installare i file dell'agente di Operations Manager in ognuno dei computer da monitorare.</span><span class="sxs-lookup"><span data-stu-id="0da50-105">To make this possible, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="0da50-106">Dopo aver installato i file dell'agente, è necessario configurare il computer per fungere da proxy del centro di sistema.</span><span class="sxs-lookup"><span data-stu-id="0da50-106">After the agent files have been installed, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="0da50-107">Tieni presente che queste procedure devono essere eseguite dopo l'installazione e la configurazione di Lync Server in questi computer.</span><span class="sxs-lookup"><span data-stu-id="0da50-107">Note that these procedures should be carried out after you have installed and configured Lync Server on these computers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

