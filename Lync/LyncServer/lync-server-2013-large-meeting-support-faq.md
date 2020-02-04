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
ms.openlocfilehash: 6f5a8d63fddf3b8633ebf31651d501458eaf4893
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a>Domande frequenti sul supporto per riunioni di grandi dimensioni per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

Nelle sezioni seguenti vengono fornite le risposte alle domande comuni per la creazione e l'uso di riunioni di grandi dimensioni.

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a>D: quante utenti possono partecipare a una riunione di grandi dimensioni?

Il modello utente di Lync Server specifica i limiti degli utenti di 250 in un pool condiviso o 1000 utenti in un pool dedicato alle riunioni di grandi dimensioni, ma questi numeri rappresentano solo il numero di utenti che abbiamo testato e solo per il set specifico di hardware usato nei test. In base al test, consigliamo i limiti per le dimensioni massime. Tuttavia, è possibile controllare il numero effettivo di partecipanti consentiti nelle riunioni dell'organizzazione configurando uno o più criteri di conferenza (che vengono configurati con i cmdlet di Windows PowerShell in Lync Server Management Shell o tramite Lync Server Pannello di controllo). Il numero specificato in un criterio di conferenza può essere qualsiasi numero intero di 32 bit compreso tra 1 e 4.294.967.295, ma le dimensioni consigliate sono comprese tra 2 e 250 partecipanti, inclusi; e il valore predefinito è 250.

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a>D: quante riunioni o altri carichi di lavoro è possibile avere in un pool dedicato alle riunioni di grandi dimensioni?

Per garantire la migliore esperienza utente in riunioni di grandi dimensioni fino a 1000 partecipanti, è consigliabile ospitare solo una riunione di grandi dimensioni alla volta in un pool dedicato alle riunioni di grandi dimensioni. Si consiglia inoltre di non consentire l'esecuzione di altri carichi di lavoro su tale pool quando è in corso una riunione di grandi dimensioni.

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a>D: gli organizzatori di una riunione di grandi dimensioni devono essere ospitati nel pool dedicato?

Non. Ti consigliamo di non dirigere gli utenti a parte il personale dedicato che gestisce la pianificazione di riunioni di grandi dimensioni nel pool dedicato. In questo modo, il traffico di comunicazioni in tempo reale viene impedito causando problemi con riunioni di grandi dimensioni ospitate nel pool. È consigliabile pianificare riunioni di grandi dimensioni nel pool dedicato usando un account utente del personale di pianificazione della riunione di grandi dimensioni. È necessario aggiungere l'account utente dell'organizzatore della riunione (l'utente che richiede una riunione di grandi dimensioni) come relatore per la riunione di grandi dimensioni.

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a>D: quali modalità multimediali è possibile usare in una riunione di grandi dimensioni?

Le riunioni di grandi dimensioni con gli utenti fino a 1000 possono includere audio, video, condivisione di PowerPoint, lavagne e polling della presenza.

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a>D: è possibile usare la messaggistica istantanea di gruppo in riunioni di grandi dimensioni?

Sì. Tuttavia, un numero elevato di messaggi istantanei, soprattutto se inviati da numerosi partecipanti alla riunione, può influire sull'esperienza utente a causa di problemi di scorrimento rapido del testo nella finestra di messaggistica istantanea. La distribuzione di un numero elevato di messaggi istantanei a un massimo di 1000 utenti può anche introdurre carichi significativi del server, che possono influire sulle prestazioni. In genere, la messaggistica istantanea è necessaria solo per domande e\&risposte (Q As).

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a>Gli utenti possono partecipare a riunioni di grandi dimensioni componendo da un telefono?

Sì. Se il pool di Lync Server 2013 è stato distribuito correttamente e abilitato per i servizi di conferenza telefonica con accesso esterno, gli utenti potranno partecipare alle riunioni di grandi dimensioni effettuando la chiamata. I nostri test hanno dimostrato che fino al 15% degli utenti di 1000 possono partecipare alla riunione di grandi dimensioni per un periodo di 10 minuti.

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a>D: è possibile ospitare riunioni di grandi dimensioni in una topologia virtuale?

Non sono state testate riunioni di grandi dimensioni in una topologia virtuale, quindi non è supportato l'uso di macchine virtuali per ospitare un pool dedicato per riunioni di grandi dimensioni.

</div>

</div>

<span> </span>

</div>

</div>

</div>

