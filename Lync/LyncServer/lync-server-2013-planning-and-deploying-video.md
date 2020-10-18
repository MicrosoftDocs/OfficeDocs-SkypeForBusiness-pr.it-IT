---
title: 'Lync Server 2013: pianificazione e distribuzione di video'
description: 'Lync Server 2013: pianificazione e distribuzione di video.'
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
ms.openlocfilehash: b9fd8a93f890295daebd2bc887414a2417b86395
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578172"
---
# <a name="planning-and-deploying-video-in-lync-server-2013"></a><span data-ttu-id="76a13-103">Pianificazione e distribuzione di video in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76a13-103">Planning and deploying video in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76a13-104">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="76a13-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="76a13-105">Lync Server 2013 introduce le nuove funzionalità video seguenti:</span><span class="sxs-lookup"><span data-stu-id="76a13-105">Lync Server 2013 introduces the following new video features:</span></span>

  - <span data-ttu-id="76a13-106">**Video HD**     Gli utenti possono sperimentare risoluzioni fino a Full High Definition (HD) (ovvero 1920 x 1080) in chiamate a due o più partecipanti.</span><span class="sxs-lookup"><span data-stu-id="76a13-106">**HD video**   Users can experience resolutions up to full high definition (HD) (that is, 1920 x 1080) in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="76a13-107">**Visualizzazione raccolta**     Nelle conferenze video che hanno più di due persone, gli utenti possono visualizzare i video dei partecipanti alla conferenza.</span><span class="sxs-lookup"><span data-stu-id="76a13-107">**Gallery View**   In video conferences that have more than two people, users can see videos of participants in the conference.</span></span> <span data-ttu-id="76a13-108">Se la conferenza ha più di cinque partecipanti, il video dei partecipanti solo più attivi viene visualizzato nella riga superiore e viene visualizzata una foto per gli altri partecipanti.</span><span class="sxs-lookup"><span data-stu-id="76a13-108">If the conference has more than five participants, video of only the most active participants appears in the top row, and a photo appears for the other participants.</span></span>

  - <span data-ttu-id="76a13-109">Video H. **264**     Il codec video H. 264 è ora il valore predefinito per la codifica video nei client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="76a13-109">**H.264 video**   The H.264 video codec is now the default for encoding video on Lync 2013 clients.</span></span> <span data-ttu-id="76a13-110">Il video H.264 supporta una grande varietà di risoluzioni video e frequenze dei fotogrammi e migliora la scalabilità video.</span><span class="sxs-lookup"><span data-stu-id="76a13-110">H.264 video supports a greater range of resolutions and frame rates, and improves video scalability.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="76a13-111">Lync Server 2013 supporta ancora il codec VC1 per l'interoperabilità con le versioni precedenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="76a13-111">Lync Server 2013 still supports the VC1 codec for interoperability with previous versions of Lync.</span></span> <span data-ttu-id="76a13-112">Per informazioni dettagliate e di base sul nuovo codec video, vedere l'articolo del Blog di Jeff Schertz, "video interoperabilità in Lync 2013", all'indirizzo <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A> .</span><span class="sxs-lookup"><span data-stu-id="76a13-112">For details and background information about the new video codec, see Jeff Schertz's Blog article, "Video Interoperability in Lync 2013," at <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span></span>

    
    </div>

<span data-ttu-id="76a13-113">In questa sezione viene descritto come gestire la larghezza di banda per i video in Lync Server 2013 e come configurare le funzionalità video.</span><span class="sxs-lookup"><span data-stu-id="76a13-113">This section describes how to manage bandwidth for video in Lync Server 2013 and how to configure video features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="76a13-114">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="76a13-114">In This Section</span></span>

  - [<span data-ttu-id="76a13-115">Configurazione della larghezza di banda video in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76a13-115">Configuring video bandwidth in Lync Server 2013</span></span>](lync-server-2013-configuring-video-bandwidth.md)

  - [<span data-ttu-id="76a13-116">Configurazione della visualizzazione raccolta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76a13-116">Configuring Gallery View in Lync Server 2013</span></span>](lync-server-2013-configuring-gallery-view.md)

  - [<span data-ttu-id="76a13-117">Configurazione di scenari di esempio video per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76a13-117">Configuring video example scenarios for Lync Server 2013</span></span>](lync-server-2013-configuring-video-example-scenarios.md)

  - [<span data-ttu-id="76a13-118">Considerazioni sull'interoperabilità per le conferenze video in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76a13-118">Interoperability considerations for video conferencing in Lync Server 2013</span></span>](lync-server-2013-interoperability-considerations-for-video-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

