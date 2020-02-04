---
title: 'Lync Server 2013: processo di pianificazione per riunioni di grandi dimensioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2cfe26b70db612249ca840c86b41fb3d60db663
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a>Processo di pianificazione delle riunioni di grandi dimensioni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

Poiché è supportata solo una riunione di grandi dimensioni alla volta nel pool di riunioni di grandi dimensioni dedicato, è consigliabile implementare un processo di pianificazione delle riunioni di grandi dimensioni per evitare conflitti di riunione di grandi dimensioni. Lo scopo di questo processo di pianificazione è facilitare la configurazione di riunioni di grandi dimensioni. Tale funzionalità non viene fornita direttamente da client Lync Server o Lync Server. Un modo per implementare un processo di questo tipo consiste nell'usare il sistema di ticketing del team di supporto dell'organizzazione, se disponibile.

Per gli organizzatori di riunioni di grandi dimensioni, la pianificazione di una riunione di grandi dimensioni prevede il completamento dei passaggi seguenti:

1.  L'organizzatore o il delegato della riunione determina l'ora, la durata e le dimensioni di una riunione imminente, oltre all'elenco di relatori. Se la dimensione prevista della riunione supera gli utenti di 250 o per garantire la migliore esperienza utente per una riunione con meno di 250 utenti, l'organizzatore o il delegato invia una richiesta per una riunione di grandi dimensioni.

2.  Il personale di pianificazione controlla se la data e l'ora richieste sono disponibili. Poiché supportiamo solo una singola riunione di grandi dimensioni nel pool dedicato alla volta, il personale di pianificazione deve controllare il calendario della riunione di grandi dimensioni per determinare se è prevista un'altra riunione per la data e l'ora richieste. Se il tempo richiesto è disponibile, il personale approva la convocazione di riunione.

3.  Se la richiesta è approvata, il personale di pianificazione (usando le credenziali nel pool dedicato) usa il componente aggiuntivo riunione online per Lync 2013 con Outlook per configurare una riunione nel pool di grandi riunioni dedicato. L'URL da usare per partecipare alla riunione viene fornito al richiedente come parte della notifica di approvazione.

4.  L'organizzatore o il delegato della riunione usa Outlook per pianificare la riunione imminente, aggiungendo l'URL per partecipare alla riunione all'invito alla riunione. L'organizzatore della riunione o il delegato specifica quindi agli utenti di essere invitati e invia l'invito alla riunione.
    
    La figura seguente illustra un flusso di lavoro di richiesta e approvazione tipico per la pianificazione di riunioni di grandi dimensioni.
    
    ![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")  

</div>

<span> </span>

</div>

</div>

</div>

