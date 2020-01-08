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

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Considerazioni sull'interoperabilità per i servizi di conferenza video in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-02_

Questa sezione descrive l'esperienza utente durante la fase di coesistenza della migrazione, quando esiste l'interoperabilità tra client legacy e un pool di Lync Server 2013 o client Lync Server 2013 e un pool legacy.

<div>

## <a name="lync-server-2013-pools"></a>Pool di Lync Server 2013

Gli utenti sperimenteranno il comportamento seguente quando un client legacy viene usato in un pool di Lync Server 2013:

  - Per le chiamate in due parti, la risoluzione video è uguale a quella del pool legacy.

  - Per le conferenze con più parti, le caratteristiche di risoluzione video e videoconferenza sono le stesse del pool legacy. La visualizzazione raccolta e la risoluzione elevata non sono disponibili.

</div>

<div>

## <a name="legacy-pools"></a>Pool legacy

Gli utenti sperimenteranno il comportamento seguente quando un client Lync Server 2013 viene usato in un pool legacy:

  - Per le chiamate in due parti, i client di Lync Server 2013 possono usare le nuove caratteristiche come segue:
    
      - H. 264 è disponibile se entrambi i partecipanti usano client Lync Server 2013.
    
      - Il client Lync Server 2013 usa il valore predefinito per TotalReceiveVideoBitRateKb, poiché il server legacy non invia queste informazioni con il provisioning in banda.

  - Per le conferenze con più parti, le caratteristiche di risoluzione video e videoconferenza sono le stesse sperimentate da un client legacy nel pool legacy.

<div>


> [!NOTE]  
> Quando un server legacy ospita un client Lync Server 2013, è possibile configurare la larghezza di banda per i servizi di conferenza video in modo che tutti gli utenti del pool ricevano solo video a bassa risoluzione, ma inviano video ad alta risoluzione. Un esempio è il momento in cui MaxVideoRateAllowed è impostato su CIF-250K nella configurazione multimediale e VideoBitRateKb è impostato su 2000 kbps nei criteri di conferenza. L'effetto netto in questa situazione è che la risoluzione elevata non è possibile per gli utenti del pool.<BR>Poiché MaxVideoRateAllowed non viene più usato per i client di Lync Server 2013, non può impedire ai client Lync Server 2013 di richiedere video ad alta risoluzione. Imposta invece VideoBitRateKb nei criteri di conferenza per tutti gli utenti del pool con lo stesso valore di MaxVideoRateAllowed (ovvero CIF è impostato su 250 kbps o VGA è impostato su 600 Kbps o HD è impostato su 1500 Kbps).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

