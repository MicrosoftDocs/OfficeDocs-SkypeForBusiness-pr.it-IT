---
title: Verificare la coesistenza del pool pilota con il pool legacy
description: Verificare la coesistenza del pool pilota con il pool legacy.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b910939b59fdaed6df32ae504eb2719435a0161e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555552"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="363e7-103">Verificare la coesistenza del pool pilota con il pool legacy</span><span class="sxs-lookup"><span data-stu-id="363e7-103">Verify pilot pool coexistence with legacy pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="363e7-104">_**Ultimo argomento modificato:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="363e7-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="363e7-105">Dopo aver distribuito il pool pilota, è necessario verificare la coesistenza dei due pool utilizzando gli strumenti di amministrazione per visualizzare le informazioni dei pool.</span><span class="sxs-lookup"><span data-stu-id="363e7-105">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="363e7-106">Per i pool Lync Server 2013 e i pool legacy, è necessario utilizzare il pannello di controllo di Lync Server 2013 e gli strumenti del generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="363e7-106">For the Lync Server 2013 pools and legacy pools, you must use the Lync Server 2013 Control Panel and Topology Builder tools.</span></span>

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a><span data-ttu-id="363e7-107">Verificare che i servizi di Lync Server 2013 siano stati avviati</span><span class="sxs-lookup"><span data-stu-id="363e7-107">Verify that Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="363e7-108">Dal front end server di Lync Server 2013 passare all'applet servizi di amministrazione degli strumenti \\ .</span><span class="sxs-lookup"><span data-stu-id="363e7-108">From the Lync Server 2013 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="363e7-109">Verificare che i servizi seguenti siano in esecuzione nel Front End Server:</span><span class="sxs-lookup"><span data-stu-id="363e7-109">Verify that the following services are running on the Front End Server:</span></span>

<span data-ttu-id="363e7-110">**Servizi di Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="363e7-110">**Lync Server 2013 services**</span></span>

<span data-ttu-id="363e7-111">![Elenco dei servizi di Lync Server avviati](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Elenco dei servizi di Lync Server avviati")</span><span class="sxs-lookup"><span data-stu-id="363e7-111">![List of Lync Server Services Started](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "List of Lync Server Services Started")</span></span>

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a><span data-ttu-id="363e7-112">Aprire il pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="363e7-112">Open the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="363e7-113">Dal front end server nella distribuzione di Lync Server 2013, aprire il pannello di controllo di Lync Server 2013 e selezionare il pool Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="363e7-113">From the Front End Server in your Lync Server 2013 deployment, open the Lync Server 2013 Control Panel and select the Lync Server 2010 pool.</span></span> <span data-ttu-id="363e7-114">Ripetere la procedura per aprire il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="363e7-114">Repeat the procedure to open the Lync Server 2013 pool.</span></span>

<span data-ttu-id="363e7-115">**Aprire il Pannello di controllo di Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="363e7-115">**Open Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="363e7-116">![Finestra di dialogo Seleziona URL.](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Finestra di dialogo Seleziona URL.")</span><span class="sxs-lookup"><span data-stu-id="363e7-116">![Select URL dialog box](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Select URL dialog box")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="363e7-117">In Lync Server 2013, è necessario eseguire l'aggiornamento a Silverlight versione 5 prima di utilizzare il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="363e7-117">On Lync Server 2013, you must upgrade Silverlight to Silverlight version 5 prior to using the Lync Server Control Panel.</span></span>



</div>

<span data-ttu-id="363e7-118">Questa topologia ora include i ruoli del server Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="363e7-118">This topology now includes Lync Server 2010 and Lync Server 2013 server roles.</span></span>

<span data-ttu-id="363e7-119">**Pagina della topologia del Pannello di controllo di Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="363e7-119">**Lync Server 2013 Control Panel Topology page**</span></span>

<span data-ttu-id="363e7-120">![Pannello di controllo di Lync Server-pagina della topologia](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Pannello di controllo di Lync Server-pagina della topologia")</span><span class="sxs-lookup"><span data-stu-id="363e7-120">![Lync Server Control Panel - Topology page](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server Control Panel - Topology page")</span></span>

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a><span data-ttu-id="363e7-121">Non tentare di aprire la topologia in Generatore di topologie di Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="363e7-121">Don’t attempt to open the topology in Lync Server 2010 Topology Builder</span></span>

<span data-ttu-id="363e7-122">Se si tenta di aprire la topologia mediante il generatore di topologie di Lync Server 2010, verrà visualizzato l'errore seguente.</span><span class="sxs-lookup"><span data-stu-id="363e7-122">If you attempt to open the topology using Lync Server 2010 Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="363e7-123">La topologia può essere visualizzata solo utilizzando il generatore di topologie di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="363e7-123">The topology can only be viewed using Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="363e7-124">Il generatore di topologie di Lync Server 2013 deve essere utilizzato per creare pool sia per Lync Server 2013 che per Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="363e7-124">The Lync Server 2013 Topology Builder must be used to create pools for both Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="363e7-125">**Messaggio di errore di Generatore di topologie di Lync Server 2010**</span><span class="sxs-lookup"><span data-stu-id="363e7-125">**Lync Server 2010 Topology Builder error message**</span></span>

<span data-ttu-id="363e7-126">![Errore di snap MMC generatore di topologie di Lync Server](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Errore di snap MMC generatore di topologie di Lync Server")</span><span class="sxs-lookup"><span data-stu-id="363e7-126">![Lync Server Topology Builder MMC Snap Error](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server Topology Builder MMC Snap Error")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

