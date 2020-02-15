---
title: "Lync Server 2013: considerazioni sull'interoperabilità per le conferenze video"
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
ms.openlocfilehash: 885768cc461b7b59c37cf83b0b422bfca6c950a2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interoperability-considerations-for-video-conferencing-in-lync-server-2013"></a>Considerazioni sull'interoperabilità per le conferenze video in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

In questa sezione viene descritta l'esperienza utente durante la fase di coesistenza della migrazione, in caso di interoperabilità tra client legacy e un pool di Lync Server 2013 o di client Lync Server 2013 e di un pool legacy.

<div>

## <a name="lync-server-2013-pools"></a>Pool di Lync Server 2013

Gli utenti sperimenteranno il comportamento seguente quando un client legacy viene utilizzato in un pool di Lync Server 2013:

  - Per le chiamate a due parti, la risoluzione video è identica a quella del pool legacy.

  - Per le conferenze multiparte, la risoluzione video e le funzionalità di videoconferenza sono identiche a quelle del pool legacy. La visualizzazione Raccolta e la risoluzione elevata non sono disponibili.

</div>

<div>

## <a name="legacy-pools"></a>Pool legacy

Gli utenti sperimenteranno il comportamento seguente quando un client Lync Server 2013 viene utilizzato in un pool legacy:

  - Per le chiamate a due parti, i client di Lync Server 2013 possono utilizzare le nuove funzionalità come indicato di seguito:
    
      - H. 264 è disponibile se entrambi i partecipanti utilizzano client Lync Server 2013.
    
      - Il client Lync Server 2013 utilizza il valore predefinito per TotalReceiveVideoBitRateKb, in quanto il server legacy non invia queste informazioni con il provisioning di tipo in-band.

  - Per le conferenze multiparte, la risoluzione video e le funzionalità di videoconferenza sono identiche a quelle del client legacy nel pool legacy.

<div>


> [!NOTE]  
> Quando un server legacy ospita un client Lync Server 2013, è possibile configurare la larghezza di banda per le conferenze video in modo che tutti gli utenti presenti nel pool ricevano solo video a bassa risoluzione, ma che inviassero video ad alta risoluzione. Un esempio è quando si imposta MaxVideoRateAllowed su CIF-250K nella configurazione dei contenuti multimediali e VideoBitRateKb è impostato su 2000 kbps nei criteri di conferenza. L'effetto in questa situazione è che la risoluzione elevata non è disponibile per gli utenti del pool.<BR>Poiché MaxVideoRateAllowed non è più utilizzato per i client di Lync Server 2013, non può impedire ai client di Lync Server 2013 di richiedere video ad alta risoluzione. Impostare invece VideoBitRateKb nei criteri di conferenza per tutti gli utenti del pool sullo stesso valore di MaxVideoRateAllowed (ovvero CIF è impostato su 250 kbps oppure VGA è impostato su 600 Kbps oppure HD è impostato su 1500 Kbps).



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

