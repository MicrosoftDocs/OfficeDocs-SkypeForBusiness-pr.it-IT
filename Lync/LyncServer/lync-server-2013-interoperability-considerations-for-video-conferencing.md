---
title: "Lync Server 2013: considerazioni sull'interoperabilità per le conferenze video"
description: "Lync Server 2013: considerazioni sull'interoperabilità per le conferenze video."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89675954ea4c4f188f50aab8fb2cb49494bcc247
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543932"
---
# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a><span data-ttu-id="b88bc-103">Considerazioni sull'interoperabilità per le conferenze video in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b88bc-103">Interoperability considerations for video conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b88bc-104">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b88bc-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b88bc-105">In questa sezione viene descritta l'esperienza utente durante la fase di coesistenza della migrazione, in caso di interoperabilità tra client legacy e un pool di Lync Server 2013 o di client Lync Server 2013 e di un pool legacy.</span><span class="sxs-lookup"><span data-stu-id="b88bc-105">This section describes the user experience during the coexistence phase of migration, when there is interoperability between legacy clients and a Lync Server 2013 pool or Lync Server 2013 clients and a legacy pool.</span></span>

<div>

## <a name="lync-server-2013-pools"></a><span data-ttu-id="b88bc-106">Pool di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b88bc-106">Lync Server 2013 Pools</span></span>

<span data-ttu-id="b88bc-107">Gli utenti sperimenteranno il comportamento seguente quando un client legacy viene utilizzato in un pool di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="b88bc-107">Users will experience the following behavior when a legacy client is used in a Lync Server 2013 pool:</span></span>

  - <span data-ttu-id="b88bc-108">Per le chiamate a due parti, la risoluzione video è identica a quella del pool legacy.</span><span class="sxs-lookup"><span data-stu-id="b88bc-108">For two-party calls, video resolution is the same as in the legacy pool.</span></span>

  - <span data-ttu-id="b88bc-p101">Per le conferenze multiparte, la risoluzione video e le funzionalità di videoconferenza sono identiche a quelle del pool legacy. La visualizzazione Raccolta e la risoluzione elevata non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="b88bc-p101">For multiparty conferences, video resolution and video conferencing features are the same as in the legacy pool. Gallery View and high resolution are not available.</span></span>

</div>

<div>

## <a name="legacy-pools"></a><span data-ttu-id="b88bc-111">Pool legacy</span><span class="sxs-lookup"><span data-stu-id="b88bc-111">Legacy Pools</span></span>

<span data-ttu-id="b88bc-112">Gli utenti sperimenteranno il comportamento seguente quando un client Lync Server 2013 viene utilizzato in un pool legacy:</span><span class="sxs-lookup"><span data-stu-id="b88bc-112">Users will experience the following behavior when a Lync Server 2013 client is used in a legacy pool:</span></span>

  - <span data-ttu-id="b88bc-113">Per le chiamate a due parti, i client di Lync Server 2013 possono utilizzare le nuove funzionalità come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b88bc-113">For two-party calls, Lync Server 2013 clients can use new features as follows:</span></span>
    
      - <span data-ttu-id="b88bc-114">H. 264 è disponibile se entrambi i partecipanti utilizzano client Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b88bc-114">H.264 is available if both participants are using Lync Server 2013 clients.</span></span>
    
      - <span data-ttu-id="b88bc-115">Il client Lync Server 2013 utilizza il valore predefinito per TotalReceiveVideoBitRateKb, in quanto il server legacy non invia queste informazioni con il provisioning di tipo in-band.</span><span class="sxs-lookup"><span data-stu-id="b88bc-115">The Lync Server 2013 client uses the default value for TotalReceiveVideoBitRateKb, since the legacy server doesn’t send this information with in-band provisioning.</span></span>

  - <span data-ttu-id="b88bc-116">Per le conferenze multiparte, la risoluzione video e le funzionalità di videoconferenza sono identiche a quelle del client legacy nel pool legacy.</span><span class="sxs-lookup"><span data-stu-id="b88bc-116">For multiparty conferences, video resolution and video conferencing features are the same as experienced by a legacy client in the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b88bc-117">Quando un server legacy ospita un client Lync Server 2013, è possibile configurare la larghezza di banda per le conferenze video in modo che tutti gli utenti presenti nel pool ricevano solo video a bassa risoluzione, ma che inviassero video ad alta risoluzione.</span><span class="sxs-lookup"><span data-stu-id="b88bc-117">When a legacy server hosts a Lync Server 2013 client, it's possible to configure video conferencing bandwidth so that all users on the pool receive only low-resolution video, but send high-resolution video.</span></span> <span data-ttu-id="b88bc-118">Un esempio è quando si imposta MaxVideoRateAllowed su CIF-250K nella configurazione dei contenuti multimediali e VideoBitRateKb è impostato su 2000 kbps nei criteri di conferenza.</span><span class="sxs-lookup"><span data-stu-id="b88bc-118">An example of this is when MaxVideoRateAllowed is set to CIF-250K in the media configuration and VideoBitRateKb is set to 2000 kbps in conferencing policy.</span></span> <span data-ttu-id="b88bc-119">L'effetto in questa situazione è che la risoluzione elevata non è disponibile per gli utenti del pool.</span><span class="sxs-lookup"><span data-stu-id="b88bc-119">The net effect in this situation is that high resolution is not possible for users on the pool.</span></span><BR><span data-ttu-id="b88bc-120">Poiché MaxVideoRateAllowed non è più utilizzato per i client di Lync Server 2013, non può impedire ai client di Lync Server 2013 di richiedere video ad alta risoluzione.</span><span class="sxs-lookup"><span data-stu-id="b88bc-120">Because MaxVideoRateAllowed is no longer used for Lync Server 2013 clients, it cannot prevent Lync Server 2013 clients from requesting high-resolution video.</span></span> <span data-ttu-id="b88bc-121">Impostare invece VideoBitRateKb nei criteri di conferenza per tutti gli utenti del pool sullo stesso valore di MaxVideoRateAllowed (ovvero CIF è impostato su 250 kbps oppure VGA è impostato su 600 Kbps oppure HD è impostato su 1500 Kbps).</span><span class="sxs-lookup"><span data-stu-id="b88bc-121">Instead, set VideoBitRateKb in conferencing policy for all users on the pool to the same value as MaxVideoRateAllowed (that is, CIF is set to 250 kbps, or VGA is set to 600 kbps, or HD is set to 1500 kbps).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

