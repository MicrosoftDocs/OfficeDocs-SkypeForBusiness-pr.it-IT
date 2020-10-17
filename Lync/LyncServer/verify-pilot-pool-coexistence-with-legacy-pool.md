---
title: Verificare la coesistenza del pool pilota con il pool legacy
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
ms.openlocfilehash: 8958fbf22e096a1d9fef03afd3aac3b4656ed0e8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515933"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="025a1-102">Verificare la coesistenza del pool pilota con il pool legacy</span><span class="sxs-lookup"><span data-stu-id="025a1-102">Verify pilot pool coexistence with legacy pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="025a1-103">_**Ultimo argomento modificato:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="025a1-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="025a1-104">Dopo aver distribuito il pool pilota, è necessario verificare la coesistenza dei due pool utilizzando gli strumenti di amministrazione per visualizzare le informazioni dei pool.</span><span class="sxs-lookup"><span data-stu-id="025a1-104">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="025a1-105">Per i pool Lync Server 2013 e i pool legacy, è necessario utilizzare il pannello di controllo di Lync Server 2013 e gli strumenti del generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="025a1-105">For the Lync Server 2013 pools and legacy pools, you must use the Lync Server 2013 Control Panel and Topology Builder tools.</span></span>

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a><span data-ttu-id="025a1-106">Verificare che i servizi di Lync Server 2013 siano stati avviati</span><span class="sxs-lookup"><span data-stu-id="025a1-106">Verify that Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="025a1-107">Dal front end server di Lync Server 2013 passare all'applet servizi di amministrazione degli strumenti \\ .</span><span class="sxs-lookup"><span data-stu-id="025a1-107">From the Lync Server 2013 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="025a1-108">Verificare che i servizi seguenti siano in esecuzione nel Front End Server:</span><span class="sxs-lookup"><span data-stu-id="025a1-108">Verify that the following services are running on the Front End Server:</span></span>

<span data-ttu-id="025a1-109">**Servizi di Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="025a1-109">**Lync Server 2013 services**</span></span>

<span data-ttu-id="025a1-110">![Elenco dei servizi di Lync Server avviati](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Elenco dei servizi di Lync Server avviati")</span><span class="sxs-lookup"><span data-stu-id="025a1-110">![List of Lync Server Services Started](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "List of Lync Server Services Started")</span></span>

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a><span data-ttu-id="025a1-111">Aprire il pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="025a1-111">Open the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="025a1-112">Dal front end server nella distribuzione di Lync Server 2013, aprire il pannello di controllo di Lync Server 2013 e selezionare il pool Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="025a1-112">From the Front End Server in your Lync Server 2013 deployment, open the Lync Server 2013 Control Panel and select the Lync Server 2010 pool.</span></span> <span data-ttu-id="025a1-113">Ripetere la procedura per aprire il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="025a1-113">Repeat the procedure to open the Lync Server 2013 pool.</span></span>

<span data-ttu-id="025a1-114">**Aprire il Pannello di controllo di Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="025a1-114">**Open Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="025a1-115">![Finestra di dialogo Seleziona URL.](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Finestra di dialogo Seleziona URL.")</span><span class="sxs-lookup"><span data-stu-id="025a1-115">![Select URL dialog box](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Select URL dialog box")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="025a1-116">In Lync Server 2013, è necessario eseguire l'aggiornamento a Silverlight versione 5 prima di utilizzare il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="025a1-116">On Lync Server 2013, you must upgrade Silverlight to Silverlight version 5 prior to using the Lync Server Control Panel.</span></span>



</div>

<span data-ttu-id="025a1-117">Questa topologia ora include i ruoli del server Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="025a1-117">This topology now includes Lync Server 2010 and Lync Server 2013 server roles.</span></span>

<span data-ttu-id="025a1-118">**Pagina della topologia del Pannello di controllo di Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="025a1-118">**Lync Server 2013 Control Panel Topology page**</span></span>

<span data-ttu-id="025a1-119">![Pannello di controllo di Lync Server-pagina della topologia](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Pannello di controllo di Lync Server-pagina della topologia")</span><span class="sxs-lookup"><span data-stu-id="025a1-119">![Lync Server Control Panel - Topology page](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server Control Panel - Topology page")</span></span>

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a><span data-ttu-id="025a1-120">Non tentare di aprire la topologia in Generatore di topologie di Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="025a1-120">Don’t attempt to open the topology in Lync Server 2010 Topology Builder</span></span>

<span data-ttu-id="025a1-121">Se si tenta di aprire la topologia mediante il generatore di topologie di Lync Server 2010, verrà visualizzato l'errore seguente.</span><span class="sxs-lookup"><span data-stu-id="025a1-121">If you attempt to open the topology using Lync Server 2010 Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="025a1-122">La topologia può essere visualizzata solo utilizzando il generatore di topologie di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="025a1-122">The topology can only be viewed using Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="025a1-123">Il generatore di topologie di Lync Server 2013 deve essere utilizzato per creare pool sia per Lync Server 2013 che per Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="025a1-123">The Lync Server 2013 Topology Builder must be used to create pools for both Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="025a1-124">**Messaggio di errore di Generatore di topologie di Lync Server 2010**</span><span class="sxs-lookup"><span data-stu-id="025a1-124">**Lync Server 2010 Topology Builder error message**</span></span>

<span data-ttu-id="025a1-125">![Errore di snap MMC generatore di topologie di Lync Server](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Errore di snap MMC generatore di topologie di Lync Server")</span><span class="sxs-lookup"><span data-stu-id="025a1-125">![Lync Server Topology Builder MMC Snap Error](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server Topology Builder MMC Snap Error")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

