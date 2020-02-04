---
title: 'Lync Server 2013: creare o modificare una nuova regola di criteri di versione client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 442341c51ef6477f72fb9e88cdea5fe7fc527aa8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a>Creare o modificare una nuova regola dei criteri di versione client in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-01-21_

Le regole dei criteri di versione client definiscono le azioni che devono essere eseguite quando gli utenti tentano di accedere con client e versioni client specifici. È possibile creare o modificare singole regole per un criterio di versione client dal pannello di controllo di Lync Server 2013.

<div>


> [!IMPORTANT]  
> Le regole sono elencate in ordine di precedenza. Ad esempio, se si ha una regola che consente ai client che usano la versione 1,5 di connettersi, seguita da una regola che blocca i client che esegue una versione precedente a 2,0, la prima regola ha la precedenza e i client che usano la versione 1,5 possono connettersi.



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a>Per creare o modificare le regole dei criteri di versione client con il pannello di controllo di Lync Server

1.  [Creare o modificare un nuovo criterio di versione client in Lync server 2013 con il](lync-server-2013-create-or-modify-a-new-client-version-policy.md) pannello di controllo di Lync Server.

2.  Nella pagina **modifica criteri di versione client** eseguire una delle operazioni seguenti:
    
      - Fare clic su **nuovo** per creare una nuova regola di versione client.
    
      - Fare clic su uno dei tipi di client definiti nell'elenco e quindi fare clic su **Mostra dettagli**.
    
    <div>
    

    > [!NOTE]  
    > Puoi usare i caratteri jolly per indicare il tipo di client.

    
    </div>

3.  In **agente utente**selezionare un tipo di client.

4.  In **numero versione**eseguire le operazioni seguenti:
    
      - Nella **versione principale**Digitare il numero corrispondente alla versione principale del client.
    
      - In **versione secondaria**Digitare il numero corrispondente al rilascio secondario del client.
    
      - Nella **Build**Digitare il numero corrispondente alla versione principale e secondaria del client.
    
      - In **Aggiorna**Digitare il numero corrispondente alla versione aggiornata del client.
    
    <div>
    

    > [!NOTE]  
    > Puoi usare i caratteri jolly per indicare il numero di versione del client.

    
    </div>

5.  Per specificare l'operazione di corrispondenza per la versione client specificata nei passaggi precedenti, in **operazione di confronto**fare clic su una delle opzioni seguenti:
    
      - **Corrispondente a**
    
      - **Diverso da**
    
      - **Più recente di**
    
      - **Più recente di o corrispondente a**
    
      - **Meno recente di**
    
      - **Meno recente di o corrispondente a**

6.  Per specificare l'azione da eseguire quando si soddisfano i criteri descritti nella procedura precedente, fare clic su una delle opzioni seguenti in **azione**:
    
      - Per consentire al client di accedere, fare clic su **Consenti**.
    
      - Per consentire al client di accedere e ricevere gli aggiornamenti da Windows Server Update Service o Microsoft Update, fare clic su **Consenti e aggiorna**. Questa azione è disponibile solo se si seleziona l'agente utente **OC**.
        
        <div>
        

        > [!NOTE]  
        > Se si seleziona questa azione, la notifica verrà visualizzata la volta successiva in cui gli utenti accederanno a Lync 2013. Tale notifica comunica la disponibilità di un aggiornamento, anche se non sono stati ancora rilasciati aggiornamenti per Windows Server Update Service o per Microsoft Update. Per evitare confusione, scegliere questa azione solo dopo che gli aggiornamenti vengono resi disponibili.

        
        </div>
    
      - Per consentire al client di accedere e visualizzare un messaggio su dove scaricare un'altra versione client, fare clic su **Consenti con URL**. Devi specificare l'URL più avanti in questa procedura.
    
      - Per impedire che il client acceda, fare clic su **blocca**.
    
      - Per impedire che il client acceda e consenta al client di ricevere gli aggiornamenti da Windows Server Update Service o Microsoft Update, fare clic su **blocca e aggiorna**. Questa azione è disponibile solo se si seleziona l'agente utente **OC**.
    
      - Per impedire che il client acceda e visualizzi un messaggio su dove scaricare un'altra versione client, fare clic su **blocca con URL**. Devi specificare l'URL più avanti in questa procedura.

7.  Opzionale Se è stato fatto clic su **Consenti con URL** o **blocco con URL** nel passaggio precedente, digitare l'URL di download del client da includere nel messaggio in **URL**.

8.  Fare clic su **OK**e quindi su **conferma**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

