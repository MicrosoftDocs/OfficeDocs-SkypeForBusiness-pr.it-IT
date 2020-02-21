---
title: 'Lync Server 2013: pianificazione dei dettagli per le riunioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dd61ce47daf1898afd1fb654493ef12ebee9ff1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a>Dettagli sulla pianificazione delle riunioni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-04_

Dopo avere verificato che nel periodo di tempo richiesto non sono pianificate altre riunioni, il personale di supporto delle riunioni di grandi dimensioni che gestisce le richieste pianifica la riunione nel pool di riunioni di grandi dimensioni. Utilizzare il componente aggiuntivo per riunioni online per Lync installato con il client Lync Server 2013 per eseguire questa attività, utilizzando le credenziali di un utente abilitato per Lync Server nel pool di riunioni di grandi dimensioni dedicato.

Per assicurare la migliore esperienza utente, è importante pianificare la riunione di grandi dimensioni con i livelli di diritto di accesso appropriati e impostazioni delle riunioni specifiche per le esigenze dell'organizzatore. È consigliabile configurare le seguenti impostazioni di pianificazione nelle opzioni di riunione di Lync:

  - Usare una nuova area riunioni per ciascuna riunione di grandi dimensioni anziché riutilizzare l'area riunione dedicata.

  - Specificare il livello di accesso alla riunione come segue:
    
      - Se almeno un invitato è esterno all'organizzazione, impostare il tipo di accesso alla riunione su **Tutti gli utenti (senza restrizioni)**. Ciò consente di evitare di dover gestire una sala d'attesa di dimensioni potenzialmente grandi quando la riunione è in corso.
    
      - Se la riunione prevede solo partecipanti interni, impostare il tipo di accesso su **Tutti gli utenti dell'organizzazione**.
        
        <div>
        

        > [!NOTE]  
        > Evitare di impostare il tipo di accesso alla riunione su <STRONG>Persone invitate appartenenti alla società</STRONG> perché questa impostazione costringe gli organizzatori ad aggiungere all'elenco degli invitati tutti gli indirizzi di posta elettronica degli utenti e non è possibile invitare un gruppo di distribuzione.<BR>Evitare di impostare il tipo di accesso alla riunione su <STRONG>Solo io, l'organizzatore della riunione</STRONG> perché questa impostazione richiede che ciascun partecipante, inclusi i relatori, stiano in sala d'attesa durante l'esecuzione della riunione. La persona responsabile della riunione di grandi dimensioni deve quindi costantemente monitorare l'elenco della sala d'attesa e ammettere i nuovi utenti che si trovano in sala d'attesa.

        
        </div>

  - Selezionare l'opzione **Consenti ai chiamanti di entrare direttamente** per consentire agli utenti che accedono dall'esterno mediante chiamata telefonica di accedere alla riunione automaticamente.

  - Invitare esplicitamente gli utenti seguenti:
    
      - Organizzatore della riunione e delegato (richiedente)
    
      - L'elenco dei relatori fornito da un richiedente della riunione
    
    <div>
    

    > [!NOTE]  
    > Se il tipo di accesso alla riunione è impostato su <STRONG>Persone scelte dall'utente</STRONG>, è necessario aggiungere esplicitamente come invitato ciascun partecipante di una riunione di grandi dimensioni.

    
    </div>

  - Gestire esplicitamente i relatori anziché impostare l'opzione su uno dei valori di promozione automatica. Assicurarsi di aggiungere gli utenti seguenti come relatori:
    
      - Organizzatore della riunione e delegato (richiedente)
    
      - L'elenco dei relatori fornito dai richiedenti di riunioni di grandi dimensioni
    
    <div>
    

    > [!NOTE]  
    > Grazie alla gestione esplicita dei relatori, è possibile controllare il numero di relatori limitandolo alla quantità necessaria per rendere possibile la realizzazione di una riunione di grandi dimensioni efficace. Se la maggioranza dei partecipanti alla riunione dispone del ruolo di partecipante, si riducono le probabilità che i partecipanti assumano per errore il controllo della presentazione, eliminino una presentazione di PowerPoint, disattivino/attivino l'audio dei relatori o siano causa di altre interruzioni della riunione.

    
    </div>

  - Selezionare l'impostazione **Disattiva l'audio di tutti i partecipanti** per fare in modo che durante la riunione venga trasmesso solo l'audio dei relatori.

  - Selezionare l'impostazione **Blocca video partecipanti** per fare in modo che durante la riunione venga trasmesso solo il video dei relatori.

Nella figura seguente vengono illustrate le impostazioni consigliate per il componente aggiuntivo per riunioni online per Lync.

![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")

</div>

<span> </span>

</div>

</div>

</div>

