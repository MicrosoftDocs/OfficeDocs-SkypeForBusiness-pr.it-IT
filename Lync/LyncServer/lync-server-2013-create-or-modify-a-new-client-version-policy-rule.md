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
ms.openlocfilehash: 9207ff9d615990d0e944ac8c435561f0c937f089
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a>Creare o modificare una nuova regola di criteri di versione client in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-01-21_

Le regole dei criteri di versione client definiscono le azioni da eseguire quando gli utenti tentano di accedere con client e versioni client specifici. È possibile creare o modificare singole regole per un criterio di versione client dal pannello di controllo di Lync Server 2013.

<div>


> [!IMPORTANT]  
> Le regole sono elencate in ordine di precedenza. Ad esempio, se si dispone di una regola che consente ai client che eseguono la versione 1,5 di connettersi, seguito da una regola che blocca i client che eseguono una versione precedente a 2,0, la prima regola ha la precedenza e i client che eseguono la versione 1,5 sono consentiti per la connessione.



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a>Per creare o modificare le regole dei criteri di versione client con il pannello di controllo di Lync Server

1.  [Creare o modificare un nuovo criterio versione client in Lync server 2013 con il](lync-server-2013-create-or-modify-a-new-client-version-policy.md) pannello di controllo di Lync Server.

2.  Nella pagina **modifica criteri versione client** eseguire una delle operazioni seguenti:
    
      - Fare clic su **nuovo** per creare una nuova regola di versione client.
    
      - Fare clic su uno dei tipi di client definiti nell'elenco e quindi fare clic su **Mostra dettagli**.
    
    <div>
    

    > [!NOTE]  
    > È possibile utilizzare i caratteri jolly per indicare il tipo di client.

    
    </div>

3.  In **agente utente**, selezionare un tipo di client.

4.  In **numero di versione**eseguire le operazioni seguenti:
    
      - Nella **versione principale**Digitare il numero corrispondente alla versione principale del client.
    
      - In **versione secondaria**Digitare il numero corrispondente alla versione secondaria del client.
    
      - In **Build**Digitare il numero corrispondente alla versione principale e secondaria del client.
    
      - In **aggiornamento**Digitare il numero corrispondente alla versione aggiornata del client.
    
    <div>
    

    > [!NOTE]  
    > È possibile utilizzare i caratteri jolly per indicare il numero di versione client.

    
    </div>

5.  Per specificare l'operazione corrispondente per la versione client specificata nei passaggi precedenti, in operazione di **confronto**fare clic su una delle opzioni seguenti:
    
      - **Corrispondente a**
    
      - **Diverso da**
    
      - **Più recente di**
    
      - **Più recente di o corrispondente a**
    
      - **Meno recente di**
    
      - **Meno recente di o corrispondente a**

6.  Per specificare l'azione da eseguire quando vengono soddisfatti i criteri nei passaggi precedenti, fare clic su una delle opzioni seguenti in **azione**:
    
      - Per consentire al client di eseguire l'accesso, fare clic su **Consenti**.
    
      - Per consentire al client di eseguire l'accesso e ricevere aggiornamenti da Windows Server Update Service o Microsoft Update, fare clic su **Consenti e aggiorna**. Questa azione è disponibile solo se si seleziona l'agente utente **OC**.
        
        <div>
        

        > [!NOTE]  
        > Se si seleziona questa azione, viene visualizzata una notifica al successivo accesso degli utenti a Lync 2013. La notifica indica che è disponibile un aggiornamento, anche se non sono stati ancora rilasciati aggiornamenti per Windows Server Update Service o Microsoft Update. Per evitare confusione, è consigliabile scegliere questa azione solo quando vengono resi disponibili gli aggiornamenti.

        
        </div>
    
      - Per consentire al client di accedere e visualizzare un messaggio su dove scaricare un'altra versione client, fare clic su **Consenti con URL**. Specificare l'URL più avanti in questa procedura.
    
      - Per impedire l'accesso del client, fare clic su **blocca**.
    
      - Per impedire al client di eseguire l'accesso e consentire al client di ricevere aggiornamenti da Windows Server Update Service o Microsoft Update, fare clic su **blocca e aggiorna**. Questa azione è disponibile solo se si seleziona l'agente utente **OC**.
    
      - Per impedire al client di eseguire l'accesso e visualizzare un messaggio su dove scaricare un'altra versione client, fare clic su **blocca con URL**. Specificare l'URL più avanti in questa procedura.

7.  Optional Se si è fatto clic su **Consenti con URL** o **blocca con URL** nel passaggio precedente, digitare l'URL di download del client da includere nel messaggio in **URL**.

8.  Fare clic su **OK**, quindi fare clic su **commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

