---
title: 'Lync Server 2013: domande frequenti sul supporto per riunioni di grandi dimensioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b00c7d2713bed543dd42812d0d7c31bf75cd1d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a>Domande frequenti sul supporto per le riunioni di grandi dimensioni per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

Le sezioni seguenti forniscono risposte alle domande comuni sulla creazione e sull'esecuzione di riunioni di grandi dimensioni.

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a>D: quanti utenti possono partecipare a una riunione di grandi dimensioni?

Il modello utente di Lync Server consente di specificare i limiti di 250 utenti in un pool condiviso o 1000 utenti in un pool dedicato a riunioni di grandi dimensioni, ma questi numeri rappresentano solo il numero di utenti che sono stati testati e solo per l'insieme specifico di hardware utilizzato per il testing. In base ai test, si consiglia di utilizzare i limiti per le dimensioni massime. Tuttavia, è possibile controllare il numero effettivo di partecipanti consentiti nelle riunioni dell'organizzazione configurando uno o più criteri di conferenza (che vengono configurati utilizzando i cmdlet di Windows PowerShell in Lync Server Management Shell o utilizzando Lync Server Pannello di controllo). Il numero specificato in un criterio di conferenza può essere un numero intero di 32 bit compreso tra 1 e 4.294.967.295, ma le dimensioni consigliate sono comprese tra 2 e 250 partecipanti, inclusi. e il valore predefinito è 250.

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a>D: quante riunioni o altri carichi di lavoro si posso avere in un pool dedicato alle riunioni di grandi dimensioni?

Per offrire la migliore esperienza utente nelle riunioni di grandi dimensioni che includono fino a 1000 partecipanti, è consigliabile ospitare una sola grande riunione per volta in un pool dedicato alle riunioni di grandi dimensioni. È inoltre preferibile non consentire l'esecuzione di altri carichi di lavoro sullo stesso pool durante una riunione di questo tipo.

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a>D: gli organizzatori di riunioni di grandi dimensioni devono essere ospitati nel pool dedicato?

No. È consigliabile non ospitare nel pool dedicato utenti al di fuori del personale dedicato che gestisce la pianificazione di riunioni di grandi dimensioni. In questo modo si evita che ulteriore traffico di comunicazioni in tempo reale determini problemi con le riunioni di grandi dimensioni ospitate nel pool. È necessario pianificare le riunioni di grandi dimensioni nel pool dedicato utilizzando un account utente del personale preposto alla pianificazione delle riunioni di questo tipo. L'account utente dell'organizzatore della riunione (l'utente che richiede una riunione di grandi dimensioni) deve essere aggiunto come relatore della riunione.

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a>D: quali supporti multimediali posso usare in una riunione di grandi dimensioni?

Le riunioni di grandi dimensioni con un massimo di 1000 utenti possono includere audio, video, condivisione PowerPoint, lavagne e sondaggio delle presenze.

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a>D: posso usare la messaggistica istantanea di gruppo nelle riunioni di grandi dimensioni?

Sì. Tuttavia, un numero elevato di messaggi istantanei, specialmente se inviati da numerosi partecipanti alla riunione, può influire sull'esperienza dell'utente a causa di problemi di scorrimento rapido del testo nella finestra di messaggistica istantanea. La distribuzione di una grande quantità di messaggi istantanei fino a 1000 utenti può anche introdurre carichi significativi del server, che possono influire sulle prestazioni. In generale, la messaggistica istantanea è necessaria solo per domande e\&risposte (Q As).

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a>Gli utenti possono partecipare alle riunioni di grandi dimensioni componendo un numero da un telefono?

Sì. Se il pool di Lync Server 2013 è stato distribuito correttamente e abilitato per le conferenze telefoniche con accesso esterno, gli utenti saranno in grado di partecipare alle riunioni di grandi dimensioni componendo l'accesso. Il test ha rilevato che fino al 15% dei 1000 utenti può partecipare alla riunione per un periodo superiore ai 10 minuti.

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a>D: posso ospitare riunioni di grandi dimensioni in una topologia virtuale?

Non sono stati eseguiti test sulle riunioni di grandi dimensioni in una topologia virtuale, pertanto non l'uso delle macchine virtuali per ospitare un pool dedicato per le riunioni di grandi dimensioni non è supportato.

</div>

</div>

<span> </span>

</div>

</div>

</div>

