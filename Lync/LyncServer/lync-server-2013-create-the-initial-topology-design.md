---
title: 'Lync Server 2013: creare la progettazione della topologia iniziale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71ccdec2c39839674c6304000680ec611a48c016
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a>Creare la progettazione della topologia iniziale per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Dopo aver completato l'installazione di Lync Server 2013, strumento di pianificazione, è possibile avviare lo strumento di pianificazione e iniziare a progettare l'infrastruttura di Lync Server 2013 proposta.

<div>


> [!NOTE]  
> Lo strumento di pianificazione è uno strumento basato su procedure guidate con guide dettagliate per informare il processo decisionale nella progettazione dei siti e della topologia. Questo argomento non è una guida esaustiva, ma è sufficiente per iniziare a utilizzare lo strumento di pianificazione nelle sessioni di progettazione.



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Per iniziare a utilizzare lo strumento di pianificazione e creare un progetto iniziale

1.  Avviare lo Strumento di pianificazione di Lync Server 2013: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Strumento di pianificazione**.

2.  Dopo che lo strumento di pianificazione è stato avviato, viene visualizzata la pagina **Benvenuto allo strumento di pianificazione per Microsoft Lync Server 2013** . Per iniziare la progettazione, scegliere una delle opzioni seguenti:
    
      - **Opzione 1:**   iniziare a fare clic su **Introduzione** fornisce una serie specifica di domande sull'intervista con selezioni rilevanti per definire i criteri. Dopo aver completato la sezione iniziale del questionario di **Per iniziare**, passare alla sezione **Progetta siti** per definire l'architettura dei siti. Per completare questa opzione, procedere al passaggio 3.
    
      - **Opzione 2: la progettazione dei siti**   che fanno clic su **siti di progettazione** nella pagina di benvenuto ignora le domande relative all'intervista presentate nella sezione **Introduzione** . Le informazioni che sarebbero state raccolte rispondendo alle domande di intervista nella sezione **Introduzione** sono impostate su valori predefiniti con questa opzione. Facendo clic su **siti di progettazione**, il progettista esperto può ignorare l'intervista iniziale e modificare i valori predefiniti, in base alle esigenze, nella pagina iniziale dei **siti centrali** . Per completare questa opzione, ignorare i passaggi da 3 a 5 e iniziare dal passaggio 6.
    
      - **Opzione 3: visualizzare la topologia**   salvata se è stata già completata e salvata una topologia mediante l'utilizzo precedente dello strumento di pianificazione, è possibile ignorare la maggior parte di questi passaggi e iniziare aprendo e visualizzando la topologia. È inoltre possibile apportare modifiche e aggiornamenti alla topologia, salvarla nuovamente e quindi esportarla in Microsoft Excel o Microsoft Visio. Per completare questa opzione, ignorare i passaggi da 3 a 12 e iniziare dal passaggio 13.

3.  Fare **clic su inizia per** iniziare a progettare la topologia di Lync Server 2013.

4.  Rispondere alle domande di ogni sezione selezionando i criteri appropriati per il progetto e quindi fare clic su **Avanti** per passare alla pagina successiva della procedura guidata. Fare clic su **indietro** per apportare modifiche alle pagine precedenti.
    
    <div>
    

    > [!TIP]  
    > Ogni pagina contiene una descrizione dei criteri di selezione e alcuni consigli in base alle procedure preferite e alla pianificazione della capacità. Se si desiderano ulteriori dettagli, <STRONG>fare clic su ulteriori informazioni</STRONG> per leggere i dati dettagliati dalla documentazione relativa alla pianificazione di Lync Server 2013 nel sito Web Microsoft TechNet. Per accedere a questo sito Web, è necessario disporre di connettività Internet.

    
    </div>

5.  Selezionare le opzioni appropriate per la progettazione. Dopo la definizione dei criteri iniziali, verrà visualizzata la conferma del completamento della panoramica iniziale.

6.  Fare clic su **progetta siti** per definire il sito centrale.
    
    <div>
    

    > [!NOTE]  
    > Ogni topologia di Lync Server 2013 avrà almeno un sito centrale. La struttura può disporre di un unico sito centrale, un sito centrale con un numero di siti di succursale, un numero di siti centrali o un numero di siti centrali con siti di succursale associati a ogni sito centrale.

    
    </div>

7.  In **nome sito**Digitare il nome che identificherà questo sito centrale.

8.  Negli **utenti di Site homed**Digitare il numero previsto di utenti simultanei locali che verranno ospitati in questo sito centrale.

9.  Negli **utenti cloud homed**Digitare il numero previsto di utenti simultanei online che verranno ospitati in questo sito centrale.

10. Modificare le selezioni per la collaborazione online, gli utenti, la voce, le opzioni di distribuzione aggiuntive o le applicazioni server, in base alle esigenze.
    
    <div>
    

    > [!IMPORTANT]  
    > A questo punto della struttura è possibile selezionare o deselezionare solo le opzioni per la distribuzione. Tuttavia, è possibile configurare altre opzioni in una fase successiva dello strumento di pianificazione. Alcune opzioni non sono disponibili e non possono essere deselezionate. Inoltre, può essere necessario deselezionare un'opzione per deselezionarne un'altra. Ad esempio, se si deseleziona l'opzione VoIP <STRONG>aziendale</STRONG> in voce, vengono cancellate anche le opzioni del <STRONG>gruppo di risposta</STRONG>, <STRONG>annuncio</STRONG>e <STRONG>parcheggio di chiamata</STRONG> in applicazioni server (tutte funzionalità di VoIP aziendale).

    
    </div>

11. Dopo aver definito il nome del sito e il numero di utenti, fare clic su **Avanti**.

12. Nelle pagine seguenti sono disponibili informazioni su domini SIP, Impostazioni conferenza, impostazioni vocali e infrastruttura, messaggistica unificata di Exchange, accesso utente esterno, impostazioni chat persistente, impostazioni client, opzioni di collocazione e siti di succursale. Rispondere a queste domande nel modo appropriato.

13. L'ultima domanda richiede se si desidera creare un altro sito centrale. Se si seleziona **Sì**, lo strumento di pianificazione torna alla pagina siti centrali. Se si seleziona **No**, fare clic su **Avanti**e quindi su **Disegna** per visualizzare la visualizzazione Topologia globale di alto livello.

14. Per visualizzare una topologia esistente, fare clic su **Visualizza**.

15. Fare clic sul file XML che corrisponde alla topologia salvata in precedenza e quindi su **Apri**.

16. Nello strumento di pianificazione viene visualizzata la pagina della topologia globale. È ora possibile avviare la modifica, l'aggiornamento o la modifica della topologia utilizzando gli strumenti disponibili nello strumento di pianificazione.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Modifica della progettazione in Lync Server 2013](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

