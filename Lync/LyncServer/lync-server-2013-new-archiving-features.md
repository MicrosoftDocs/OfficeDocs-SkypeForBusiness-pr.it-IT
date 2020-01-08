---
title: 'Lync Server 2013: Nuove funzionalità di archiviazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d736e823892aa6d6edcc5ab90df900a5c6b7ac79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a>Nuove funzionalità di archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-09_

L'archiviazione in Lync Server 2013 può archiviare i tipi di contenuto seguenti:

  - Messaggi istantanei peer-to-peer

  - Conferenze (riunioni) che sono messaggi istantanei multiparte

  - Contenuto della conferenza, incluso il contenuto caricato, ad esempio gli stampati, e il contenuto correlato agli eventi (ad esempio, partecipazione, uscita, caricamento della condivisione e modifica della visibilità)

Inoltre, l'archiviazione in Lync Server 2013 offre nuove funzionalità che migliorano l'efficienza della distribuzione e delle operazioni. Queste nuove funzionalità sono costituite da:

  - **Collocazione dell'archiviazione nei server front-end.**    Lync Server 2013 non ha un ruolo di server di archiviazione distinto. L'archiviazione è una funzionalità facoltativa disponibile in tutti i server front-end in una distribuzione di Enterprise Edition e nei server Standard Edition, che possono essere implementati configurati per un pool o un sito.

  - **Integrazione di Microsoft Exchange.**    Quando si distribuisce l'archiviazione, è possibile integrare lo spazio di archiviazione dei dati per l'archiviazione con l'archiviazione di Exchange 2013 esistente per tutti gli utenti residenti in Exchange 2013 e inserire le cassette postali sul posto, quindi non è necessario distribuire database di SQL Server distinti per archiviare i dati di Lync. Se non si dispone di una distribuzione di Exchange 2013 o se si preferisce non integrarla o se si hanno utenti di Lync 2013 non residenti in Exchange 2013 con le cassette postali inserite nel blocco, è possibile distribuire database di archiviazione distinti tramite SQL Server per stor e dati archiviati da Lync Communications. È possibile usare sia l'integrazione di Microsoft Exchange che i database di archiviazione di Lync Server 2013 se si vuole usare l'integrazione di Microsoft Exchange per alcuni utenti, ma non tutti, nella distribuzione. Per informazioni dettagliate sul blocco sul posto, vedere "blocco sul posto" [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500).

  - **Mirroring di SQL Store.**    Quando si distribuisce l'archiviazione, è possibile abilitare il mirroring del database di SQL Server per il database di archiviazione.

  - **Archiviazione di lavagne e sondaggi.**    Il contenuto di una conferenza archiviata ora include lavagne e sondaggi condivisi durante la riunione.

I tipi di contenuto seguenti non vengono archiviati:

  - Trasferimenti di file peer-to-peer

  - Audio/video per i messaggi istantanei e le conferenze peer-to-peer

  - Condivisione di applicazioni per i messaggi istantanei e le conferenze peer-to-peer

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione dell'archiviazione in Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

