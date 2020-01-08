---
title: "Lync Server 2013: considerazioni sull'interoperabilità per i servizi di conferenza video"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Interoperability considerations for video conferencing
ms:assetid: 31ead3b5-ed95-42d4-96e2-7d9403d5c026
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204790(v=OCS.15)
ms:contentKeyID: 48183782
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 880b2e41a1ea92b3d6da9cd29153695b474e88f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a><span data-ttu-id="c3c07-102">Considerazioni sull'interoperabilità per i servizi di conferenza video in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3c07-102">Interoperability considerations for video conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3c07-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c3c07-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c3c07-104">Questa sezione descrive l'esperienza utente durante la fase di coesistenza della migrazione, quando esiste l'interoperabilità tra client legacy e un pool di Lync Server 2013 o client Lync Server 2013 e un pool legacy.</span><span class="sxs-lookup"><span data-stu-id="c3c07-104">This section describes the user experience during the coexistence phase of migration, when there is interoperability between legacy clients and a Lync Server 2013 pool or Lync Server 2013 clients and a legacy pool.</span></span>

<div>

## <a name="lync-server-2013-pools"></a><span data-ttu-id="c3c07-105">Pool di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3c07-105">Lync Server 2013 Pools</span></span>

<span data-ttu-id="c3c07-106">Gli utenti sperimenteranno il comportamento seguente quando un client legacy viene usato in un pool di Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="c3c07-106">Users will experience the following behavior when a legacy client is used in a Lync Server 2013 pool:</span></span>

  - <span data-ttu-id="c3c07-107">Per le chiamate in due parti, la risoluzione video è uguale a quella del pool legacy.</span><span class="sxs-lookup"><span data-stu-id="c3c07-107">For two-party calls, video resolution is the same as in the legacy pool.</span></span>

  - <span data-ttu-id="c3c07-108">Per le conferenze con più parti, le caratteristiche di risoluzione video e videoconferenza sono le stesse del pool legacy.</span><span class="sxs-lookup"><span data-stu-id="c3c07-108">For multiparty conferences, video resolution and video conferencing features are the same as in the legacy pool.</span></span> <span data-ttu-id="c3c07-109">La visualizzazione raccolta e la risoluzione elevata non sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="c3c07-109">Gallery View and high resolution are not available.</span></span>

</div>

<div>

## <a name="legacy-pools"></a><span data-ttu-id="c3c07-110">Pool legacy</span><span class="sxs-lookup"><span data-stu-id="c3c07-110">Legacy Pools</span></span>

<span data-ttu-id="c3c07-111">Gli utenti sperimenteranno il comportamento seguente quando un client Lync Server 2013 viene usato in un pool legacy:</span><span class="sxs-lookup"><span data-stu-id="c3c07-111">Users will experience the following behavior when a Lync Server 2013 client is used in a legacy pool:</span></span>

  - <span data-ttu-id="c3c07-112">Per le chiamate in due parti, i client di Lync Server 2013 possono usare le nuove caratteristiche come segue:</span><span class="sxs-lookup"><span data-stu-id="c3c07-112">For two-party calls, Lync Server 2013 clients can use new features as follows:</span></span>
    
      - <span data-ttu-id="c3c07-113">H. 264 è disponibile se entrambi i partecipanti usano client Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c3c07-113">H.264 is available if both participants are using Lync Server 2013 clients.</span></span>
    
      - <span data-ttu-id="c3c07-114">Il client Lync Server 2013 usa il valore predefinito per TotalReceiveVideoBitRateKb, poiché il server legacy non invia queste informazioni con il provisioning in banda.</span><span class="sxs-lookup"><span data-stu-id="c3c07-114">The Lync Server 2013 client uses the default value for TotalReceiveVideoBitRateKb, since the legacy server doesn’t send this information with in-band provisioning.</span></span>

  - <span data-ttu-id="c3c07-115">Per le conferenze con più parti, le caratteristiche di risoluzione video e videoconferenza sono le stesse sperimentate da un client legacy nel pool legacy.</span><span class="sxs-lookup"><span data-stu-id="c3c07-115">For multiparty conferences, video resolution and video conferencing features are the same as experienced by a legacy client in the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c3c07-116">Quando un server legacy ospita un client Lync Server 2013, è possibile configurare la larghezza di banda per i servizi di conferenza video in modo che tutti gli utenti del pool ricevano solo video a bassa risoluzione, ma inviano video ad alta risoluzione.</span><span class="sxs-lookup"><span data-stu-id="c3c07-116">When a legacy server hosts a Lync Server 2013 client, it's possible to configure video conferencing bandwidth so that all users on the pool receive only low-resolution video, but send high-resolution video.</span></span> <span data-ttu-id="c3c07-117">Un esempio è il momento in cui MaxVideoRateAllowed è impostato su CIF-250K nella configurazione multimediale e VideoBitRateKb è impostato su 2000 kbps nei criteri di conferenza.</span><span class="sxs-lookup"><span data-stu-id="c3c07-117">An example of this is when MaxVideoRateAllowed is set to CIF-250K in the media configuration and VideoBitRateKb is set to 2000 kbps in conferencing policy.</span></span> <span data-ttu-id="c3c07-118">L'effetto netto in questa situazione è che la risoluzione elevata non è possibile per gli utenti del pool.</span><span class="sxs-lookup"><span data-stu-id="c3c07-118">The net effect in this situation is that high resolution is not possible for users on the pool.</span></span><BR><span data-ttu-id="c3c07-119">Poiché MaxVideoRateAllowed non viene più usato per i client di Lync Server 2013, non può impedire ai client Lync Server 2013 di richiedere video ad alta risoluzione.</span><span class="sxs-lookup"><span data-stu-id="c3c07-119">Because MaxVideoRateAllowed is no longer used for Lync Server 2013 clients, it cannot prevent Lync Server 2013 clients from requesting high-resolution video.</span></span> <span data-ttu-id="c3c07-120">Imposta invece VideoBitRateKb nei criteri di conferenza per tutti gli utenti del pool con lo stesso valore di MaxVideoRateAllowed (ovvero CIF è impostato su 250 kbps o VGA è impostato su 600 Kbps o HD è impostato su 1500 Kbps).</span><span class="sxs-lookup"><span data-stu-id="c3c07-120">Instead, set VideoBitRateKb in conferencing policy for all users on the pool to the same value as MaxVideoRateAllowed (that is, CIF is set to 250 kbps, or VGA is set to 600 kbps, or HD is set to 1500 kbps).</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

