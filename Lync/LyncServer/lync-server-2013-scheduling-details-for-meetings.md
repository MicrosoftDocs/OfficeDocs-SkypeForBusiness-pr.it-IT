---
title: 'Lync Server 2013: pianificare i dettagli per le riunioni'
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
ms.openlocfilehash: a4a0f85e93588e725e825fee22a8c2e95b74095b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a>Dettagli della pianificazione per le riunioni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-04_

Dopo aver verificato che non sia prevista nessun'altra riunione al momento richiesto, il personale di supporto per le riunioni di grandi dimensioni che gestisce la richiesta pianifica la riunione nel pool di grandi riunioni. Usare il componente aggiuntivo riunione online per Lync installato con il client Lync Server 2013 per eseguire questa attività, usando le credenziali di un utente abilitato per Lync Server nel pool di grandi riunioni dedicato.

Per garantire la migliore esperienza utente, è importante pianificare la riunione di grandi dimensioni con i livelli di accesso corretti e le impostazioni delle riunioni appropriate per le esigenze dell'organizzatore della riunione. È consigliabile configurare le impostazioni di pianificazione seguenti nelle opzioni di riunione di Lync:

  - Usare un nuovo spazio per riunioni per ogni riunione di grandi dimensioni invece di riutilizzare lo spazio dedicato per le riunioni.

  - Specificare il livello di accesso alla riunione come indicato di seguito:
    
      - Se almeno un invitato è esterno all'organizzazione, imposta il tipo di accesso alla riunione a **chiunque (nessuna restrizione**. In questo modo è possibile evitare di dover gestire una sala di attesa potenzialmente grande quando la riunione è in corso.
    
      - Se la riunione è una riunione interna, impostare il tipo di accesso alla riunione per **tutti gli utenti dell'organizzazione**.
        
        <div>
        

        > [!NOTE]  
        > Evitare di impostare il tipo di accesso alla riunione per le <STRONG>persone che invito dalla mia società</STRONG> perché quando si usa questa impostazione, gli organizzatori devono aggiungere tutti gli indirizzi di posta elettronica dell'utente all'elenco di invitati e non è possibile invitare un gruppo di distribuzione.<BR>Evitare di impostare il tipo di accesso alla riunione <STRONG>solo a me, l'organizzatore della riunione</STRONG> perché questa impostazione richiede che ogni partecipante alla riunione, inclusi i relatori, debba essere inserito nella sala di attesa in fase di esecuzione della riunione. La persona responsabile dell'uso della riunione di grandi dimensioni deve quindi monitorare costantemente il roster della sala di attesa e ammettere nuovi utenti che si trovano nell'atrio.

        
        </div>

  - Consentire agli utenti che accedono tramite telefono di accedere automaticamente alla riunione controllando che i **chiamanti entrino direttamente nell'** impostazione.

  - Invitare esplicitamente gli utenti seguenti:
    
      - Organizzatore della riunione e delegato (richiedente)
    
      - Elenco di relatori forniti da un richiedente di una riunione
    
    <div>
    

    > [!NOTE]  
    > Se il tipo di accesso alla riunione è impostato per gli <STRONG>utenti scelti</STRONG>, è necessario aggiungere esplicitamente ogni partecipante di una riunione di grandi dimensioni come invito della riunione.

    
    </div>

  - Gestisci esplicitamente i relatori, invece di impostare l'opzione Presenter su uno dei valori di promozione automatica. Assicurarsi di aggiungere gli utenti seguenti come relatori:
    
      - Organizzatore della riunione e delegato (richiedente)
    
      - Elenco di relatori forniti da convocazione di riunione di grandi dimensioni
    
    <div>
    

    > [!NOTE]  
    > Con la gestione esplicita dei relatori, puoi controllare il numero di relatori, in modo da poter limitare i relatori a un numero abbastanza piccolo per consentire una riunione di grandi dimensioni efficace. Se la maggior parte dei partecipanti alla riunione ha il ruolo di partecipante, consente di ridurre la probabilità che le persone prendano accidentalmente il controllo della presentazione, eliminando una presentazione di PowerPoint, riattivando o disattivando i relatori e altre interruzioni alla riunione.

    
    </div>

  - Selezionare l'impostazione **Disattiva tutti i partecipanti** per verificare che solo i relatori possano trasmettere l'audio alla riunione.

  - Controlla l'impostazione del **video dei partecipanti al blocco** per verificare che solo i relatori possano trasmettere video alla riunione.

La figura seguente mostra le impostazioni consigliate per il componente aggiuntivo riunione online per Lync.

![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")

</div>

<span> </span>

</div>

</div>

</div>

