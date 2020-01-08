---
title: Verificare la coesistenza del pool pilota con il pool legacy
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7de258bff926e2e100fa7c9a4952a4d70ca64373
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a><span data-ttu-id="f037e-102">Verificare la coesistenza del pool pilota con il pool legacy</span><span class="sxs-lookup"><span data-stu-id="f037e-102">Verify pilot pool coexistence with legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f037e-103">_**Argomento Ultima modifica:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="f037e-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="f037e-104">Dopo la distribuzione del pool pilota, è necessario verificare la coesistenza dei due pool usando gli strumenti di amministrazione per visualizzare le informazioni sul pool.</span><span class="sxs-lookup"><span data-stu-id="f037e-104">After you deploy the pilot pool, you need to verify the coexistence of the two pools by using the administrative tools to view the pool information.</span></span> <span data-ttu-id="f037e-105">Per i pool di Lync Server 2013 e i pool legacy, è necessario usare il pannello di controllo e gli strumenti del generatore di topologia di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f037e-105">For the Lync Server 2013 pools and legacy pools, you must use the Lync Server 2013 Control Panel and Topology Builder tools.</span></span>

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a><span data-ttu-id="f037e-106">Verificare che i servizi di Lync Server 2013 siano stati avviati</span><span class="sxs-lookup"><span data-stu-id="f037e-106">Verify that Lync Server 2013 services have started</span></span>

1.  <span data-ttu-id="f037e-107">Dal server front-end di Lync Server 2013 passare all'applet strumenti\\di amministrazione di servizi.</span><span class="sxs-lookup"><span data-stu-id="f037e-107">From the Lync Server 2013 Front End Server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="f037e-108">Verificare che i servizi seguenti siano in uso nel server front-end:</span><span class="sxs-lookup"><span data-stu-id="f037e-108">Verify that the following services are running on the Front End Server:</span></span>

<span data-ttu-id="f037e-109">**Servizi di Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="f037e-109">**Lync Server 2013 services**</span></span>

<span data-ttu-id="f037e-110">![Elenco dei servizi di Lync Server avviati](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "elenco dei servizi Lync Server avviati")</span><span class="sxs-lookup"><span data-stu-id="f037e-110">![List of Lync Server Services Started](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "List of Lync Server Services Started")</span></span>

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a><span data-ttu-id="f037e-111">Aprire il pannello di controllo di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f037e-111">Open the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="f037e-112">Dal server front-end nella distribuzione di Lync Server 2013 aprire il pannello di controllo di Lync Server 2013 e selezionare il pool di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f037e-112">From the Front End Server in your Lync Server 2013 deployment, open the Lync Server 2013 Control Panel and select the Lync Server 2010 pool.</span></span> <span data-ttu-id="f037e-113">Ripetere la procedura per aprire il pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f037e-113">Repeat the procedure to open the Lync Server 2013 pool.</span></span>

<span data-ttu-id="f037e-114">**Aprire il pannello di controllo di Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="f037e-114">**Open Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="f037e-115">Finestra di dialogo ![Seleziona]URL selezionare la finestra di dialogo(images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "URL")</span><span class="sxs-lookup"><span data-stu-id="f037e-115">![Select URL dialog box](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Select URL dialog box")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f037e-116">In Lync Server 2013 è necessario eseguire l'aggiornamento a Silverlight versione 5 prima di usare il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f037e-116">On Lync Server 2013, you must upgrade Silverlight to Silverlight version 5 prior to using the Lync Server Control Panel.</span></span>



</div>

<span data-ttu-id="f037e-117">Questa topologia ora include i ruoli del server Lync Server 2010 e Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f037e-117">This topology now includes Lync Server 2010 and Lync Server 2013 server roles.</span></span>

<span data-ttu-id="f037e-118">**Pagina della topologia del pannello di controllo di Lync Server 2013**</span><span class="sxs-lookup"><span data-stu-id="f037e-118">**Lync Server 2013 Control Panel Topology page**</span></span>

<span data-ttu-id="f037e-119">![Pannello di controllo di Lync Server-pagina topologia](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Pannello di controllo di Lync Server-pagina topologia")</span><span class="sxs-lookup"><span data-stu-id="f037e-119">![Lync Server Control Panel - Topology page](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server Control Panel - Topology page")</span></span>

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a><span data-ttu-id="f037e-120">Non provare ad aprire la topologia in Generatore di topologia di Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f037e-120">Don’t attempt to open the topology in Lync Server 2010 Topology Builder</span></span>

<span data-ttu-id="f037e-121">Se si tenta di aprire la topologia con il generatore di topologia di Lync Server 2010, si verificherà l'errore seguente.</span><span class="sxs-lookup"><span data-stu-id="f037e-121">If you attempt to open the topology using Lync Server 2010 Topology Builder, you will encounter the error below.</span></span> <span data-ttu-id="f037e-122">La topologia può essere visualizzata solo con il generatore di topologia di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f037e-122">The topology can only be viewed using Lync Server 2013 Topology Builder.</span></span> <span data-ttu-id="f037e-123">Il generatore di topologia di Lync Server 2013 deve essere usato per creare pool sia per Lync Server 2013 che per Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f037e-123">The Lync Server 2013 Topology Builder must be used to create pools for both Lync Server 2013 and Lync Server 2010.</span></span>

<span data-ttu-id="f037e-124">**Messaggio di errore del generatore di topologia di Lync Server 2010**</span><span class="sxs-lookup"><span data-stu-id="f037e-124">**Lync Server 2010 Topology Builder error message**</span></span>

<span data-ttu-id="f037e-125">Errore(images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "di snap-") in MMC generatore di topologia ![di Lync Server]</span><span class="sxs-lookup"><span data-stu-id="f037e-125">![Lync Server Topology Builder MMC Snap Error](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server Topology Builder MMC Snap Error")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

