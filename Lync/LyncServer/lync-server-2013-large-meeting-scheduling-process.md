---
title: 'Lync Server 2013: processo di pianificazione delle riunioni di grandi dimensioni'
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
ms.openlocfilehash: 3ccbe1735d92d510f4e5016cc2e52b62e1c82bb7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a>Processo di pianificazione delle riunioni di grandi dimensioni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

Dato che nel pool dedicato per le riunioni di grandi dimensioni è supportata una sola riunione di grandi dimensioni alla volta, è consigliabile implementare un processo per la pianificazione di questo tipo di riunioni in modo da evitare conflitti. Lo scopo di tale processo di pianificazione è agevolare la configurazione delle riunioni di grandi dimensioni. Tale funzionalità non viene fornita direttamente dai client Lync Server o Lync Server. Un metodo per implementare un processo di questo tipo consiste nell'utilizzare il sistema di gestione dei ticket del team di supporto tecnico dell'organizzazione, se disponibile.

Per gli organizzatori di riunioni di grandi dimensioni, la pianificazione include l'esecuzione dei passaggi seguenti:

1.  L'organizzatore della riunione o il delegato stabilisce data e ora, durata e dimensioni di una riunione prossima, oltre all'elenco dei relatori. Se le dimensioni previste per la riunione superano i 250 utenti oppure per assicurare un'esperienza utente ottimale per una riunione con meno di 250 utenti, l'organizzatore o il delegato invia una richiesta per una riunione di grandi dimensioni.

2.  Il personale addetto della pianificazione verifica se la data e l'ora richieste sono disponibili. Dato che nel pool dedicato è supportata una sola riunione di grandi dimensioni alla volta, il personale addetto alla pianificazione deve controllare il calendario di questo tipo di riunioni per stabilire se ne è già presente un'altra pianificata per la data e l'ora richieste. Se l'intervallo di tempo richiesto risulta disponibile, la richiesta di riunione viene approvata.

3.  Se la richiesta viene approvata, il personale di pianificazione (utilizzando le credenziali nel pool dedicato) utilizza il componente aggiuntivo per riunioni online per Lync 2013 con Outlook per impostare una riunione nel pool di riunioni di grandi dimensioni dedicato. L'URL da utilizzare per partecipare alla riunione viene fornito al richiedente nell'ambito della notifica dell'approvazione.

4.  L'organizzatore della riunione o il delegato utilizza Outlook per pianificare la riunione imminente, aggiungendo l'URL per la partecipazione alla riunione all'invito alla riunione. L'organizzatore della riunione o il delegato specifica quindi gli utenti da invitare e invia l'invito alla riunione.
    
    Nella figura seguente sono illustrati una richiesta e un flusso di lavoro di approvazione tipici per la pianificazione di riunioni di grandi dimensioni.
    
    ![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")  

</div>

<span> </span>

</div>

</div>

</div>

