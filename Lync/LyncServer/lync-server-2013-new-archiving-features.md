---
title: 'Lync Server 2013: nuove funzionalità di archiviazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89a8969924acdf8268f059ae3b3660b70ca1dca7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a>Nuove funzionalità di archiviazione in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-09_

L'archiviazione in Lync Server 2013 è in grado di archiviare i tipi di contenuto seguenti:

  - Messaggi istantanei peer-to-peer

  - Conferenze (riunioni) costituite da messaggi istantanei tra più parti

  - Contenuto di conferenze, compreso il contenuto caricato (ad esempio, gli stampati) e correlato agli eventi (ad esempio, accesso, uscita, caricamento in condivisione e modifiche della visibilità)

Inoltre, l'archiviazione in Lync Server 2013 fornisce nuove funzionalità che migliorano la distribuzione e l'efficienza delle operazioni. Queste nuove funzionalità sono le seguenti:

  - **Collocazione dell'archiviazione nei Front End Server.**    Lync Server 2013 non dispone di un ruolo del server di archiviazione distinto. L'archiviazione infatti è una funzionalità facoltativa, disponibile in tutti i Front End Server di una distribuzione Enterprise Edition e nei server Standard Edition, che può essere implementata e configurata per un pool o un sito.

  - **Integrazione di Microsoft Exchange.**    Quando si distribuisce l'archiviazione, è possibile integrare l'archiviazione dei dati per l'archiviazione con l'archivio di Exchange 2013 esistente per tutti gli utenti che si trovano in Exchange 2013 e che le cassette postali vengono conservate sul posto, pertanto non è necessario distribuire database di SQL Server distinti per archiviare i dati di Lync. Se non si dispone di una distribuzione di Exchange 2013 o se si preferisce non integrarlo o se sono presenti utenti di Lync 2013 che non sono ospitati in Exchange 2013 con le proprie cassette postali in blocco sul posto, è possibile distribuire database di archiviazione separati utilizzando SQL Server per stor e dati archiviati da Lync Communications. È possibile utilizzare l'integrazione di Microsoft Exchange e i database di archiviazione di Lync Server 2013 se si desidera utilizzare l'integrazione di Microsoft Exchange per alcuni ma non tutti gli utenti nella distribuzione. Per informazioni dettagliate sull'archiviazione sul posto, vedere "blocco sul posto" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500).

  - **Mirroring dell'archivio SQL.**    Quando si distribuisce l'archiviazione, è possibile abilitare il mirroring del database di SQL Server per il database di archiviazione.

  - **Archiviazione di lavagne e sondaggi.**    Il contenuto delle conferenze archiviate ora include le lavagne e i sondaggi condivisi durante la riunione.

Non vengono archiviati i tipi di contenuto seguenti:

  - Trasferimenti di file peer-to-peer

  - Audio e video per conferenze e messaggi istantanei peer-to-peer

  - Condivisione di applicazioni per conferenze e messaggi istantanei peer-to-peer

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione dell'archiviazione in Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

