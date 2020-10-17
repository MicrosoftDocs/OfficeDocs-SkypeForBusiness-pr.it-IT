---
title: 'Lync Server 2013: pianificazione e distribuzione di video'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning and deploying video
ms:assetid: dadfb7f3-dfd6-4847-b137-17dacafd7368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205307(v=OCS.15)
ms:contentKeyID: 48185558
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf5eca9118c9f4706aa209dc1e2db1b3dbbed358
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519813"
---
# <a name="planning-and-deploying-video-in-lync-server-2013"></a><span data-ttu-id="b40fe-102">Pianificazione e distribuzione di video in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b40fe-102">Planning and deploying video in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b40fe-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b40fe-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b40fe-104">Lync Server 2013 introduce le nuove funzionalità video seguenti:</span><span class="sxs-lookup"><span data-stu-id="b40fe-104">Lync Server 2013 introduces the following new video features:</span></span>

  - <span data-ttu-id="b40fe-105">**Video HD**     Gli utenti possono sperimentare risoluzioni fino a Full High Definition (HD) (ovvero 1920 x 1080) in chiamate a due o più partecipanti.</span><span class="sxs-lookup"><span data-stu-id="b40fe-105">**HD video**   Users can experience resolutions up to full high definition (HD) (that is, 1920 x 1080) in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="b40fe-106">**Visualizzazione raccolta**     Nelle conferenze video che hanno più di due persone, gli utenti possono visualizzare i video dei partecipanti alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="b40fe-106">**Gallery View**   In video conferences that have more than two people, users can see videos of participants in the conference.</span></span> <span data-ttu-id="b40fe-107">Se la conferenza ha più di cinque partecipanti, il video dei partecipanti solo più attivi viene visualizzato nella riga superiore e viene visualizzata una foto per gli altri partecipanti.</span><span class="sxs-lookup"><span data-stu-id="b40fe-107">If the conference has more than five participants, video of only the most active participants appears in the top row, and a photo appears for the other participants.</span></span>

  - <span data-ttu-id="b40fe-108">Video H. **264**     Il codec video H. 264 è ora il valore predefinito per la codifica video nei client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b40fe-108">**H.264 video**   The H.264 video codec is now the default for encoding video on Lync 2013 clients.</span></span> <span data-ttu-id="b40fe-109">Il video H.264 supporta una grande varietà di risoluzioni video e frequenze dei fotogrammi e migliora la scalabilità video.</span><span class="sxs-lookup"><span data-stu-id="b40fe-109">H.264 video supports a greater range of resolutions and frame rates, and improves video scalability.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b40fe-110">Lync Server 2013 supporta ancora il codec VC1 per l'interoperabilità con le versioni precedenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="b40fe-110">Lync Server 2013 still supports the VC1 codec for interoperability with previous versions of Lync.</span></span> <span data-ttu-id="b40fe-111">Per informazioni dettagliate e di base sul nuovo codec video, vedere l'articolo del Blog di Jeff Schertz, "video interoperabilità in Lync 2013", all'indirizzo <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A> .</span><span class="sxs-lookup"><span data-stu-id="b40fe-111">For details and background information about the new video codec, see Jeff Schertz's Blog article, "Video Interoperability in Lync 2013," at <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span></span>

    
    </div>

<span data-ttu-id="b40fe-112">In questa sezione viene descritto come gestire la larghezza di banda per i video in Lync Server 2013 e come configurare le funzionalità video.</span><span class="sxs-lookup"><span data-stu-id="b40fe-112">This section describes how to manage bandwidth for video in Lync Server 2013 and how to configure video features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b40fe-113">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="b40fe-113">In This Section</span></span>

  - [<span data-ttu-id="b40fe-114">Configurazione della larghezza di banda video in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b40fe-114">Configuring video bandwidth in Lync Server 2013</span></span>](lync-server-2013-configuring-video-bandwidth.md)

  - [<span data-ttu-id="b40fe-115">Configurazione della visualizzazione raccolta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b40fe-115">Configuring Gallery View in Lync Server 2013</span></span>](lync-server-2013-configuring-gallery-view.md)

  - [<span data-ttu-id="b40fe-116">Configurazione di scenari di esempio video per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b40fe-116">Configuring video example scenarios for Lync Server 2013</span></span>](lync-server-2013-configuring-video-example-scenarios.md)

  - [<span data-ttu-id="b40fe-117">Considerazioni sull'interoperabilità per le conferenze video in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b40fe-117">Interoperability considerations for video conferencing in Lync Server 2013</span></span>](lync-server-2013-interoperability-considerations-for-video-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

