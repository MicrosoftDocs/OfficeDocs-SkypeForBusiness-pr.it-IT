---
title: 'Lync Server 2013: creare la struttura della topologia iniziale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create the initial design
ms:assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615047(v=OCS.15)
ms:contentKeyID: 51541530
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 656e9605695fe7dab160469ffa9e9c5075ac807b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980034"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-initial-topology-design-for-lync-server-2013"></a>Creare la struttura della topologia iniziale per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Dopo aver completato l'installazione di Lync Server 2013, strumento di pianificazione, si è pronti per avviare lo strumento di pianificazione e iniziare a progettare l'infrastruttura di Lync Server 2013 proposta.

<div>


> [!NOTE]  
> Lo strumento di pianificazione è uno strumento basato su una procedura guidata con guide dettagliate per informare il processo decisionale nella progettazione di siti e topologia. Questo argomento è inteso come guida esaustiva, ma semplicemente per iniziare a usare lo strumento pianificazione nelle sessioni di progettazione.



</div>

<div>

## <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Per iniziare a usare lo strumento pianificazione e creare la struttura iniziale

1.  Avviare Lync Server 2013, strumento di pianificazione: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **strumento di pianificazione**.

2.  Dopo l'avvio dello strumento di pianificazione, viene visualizzata la pagina **Benvenuto nello strumento di pianificazione per Microsoft Lync Server 2013** . Per iniziare la progettazione, scegliere una delle opzioni seguenti:
    
      - **Opzione 1:**   iniziare a fare **clic su per iniziare offre** una serie specifica di domande sulle interviste con selezioni rilevanti per definire i criteri. Dopo aver completato la sezione iniziale dell'intervista **introduttiva** , si procede in **siti di progettazione** per definire l'architettura del sito. Per completare questa opzione, procedere con il passaggio 3.
    
      - **Opzione 2: i siti**   di progettazione che fanno clic su **siti di progettazione** nella pagina di benvenuto ignorano le domande sull'intervista presentate nella sezione iniziare. **** Le informazioni che sarebbero state raccolte rispondendo alle domande sull'intervista nella sezione **Introduzione** sono impostate su valori predefiniti con questa opzione. Facendo clic su **siti di progettazione**, il progettista esperto può ignorare l'intervista iniziale e modificare i valori predefiniti, se necessario, nella pagina iniziale dei **siti centrali** . Per completare questa opzione, saltare i passaggi 3-5 e iniziare dal passaggio 6.
    
      - **Opzione 3: visualizzare la topologia**   salvata se è già stata completata e salvata una topologia con l'uso precedente dello strumento di pianificazione, è possibile ignorare la maggior parte di questi passaggi e iniziare aprendo e visualizzando la topologia. È anche possibile apportare modifiche e aggiornamenti alla topologia, salvarla e quindi esportarla in Microsoft Excel o Microsoft Visio. Per completare questa opzione, saltare i passaggi 3-12 e iniziare dal passaggio 13.

3.  Fare **clic su inizia per** iniziare a progettare la topologia di Lync Server 2013.

4.  Rispondere a ogni sezione selezionando i criteri appropriati per la struttura e quindi fare clic su **Avanti** per passare alla pagina successiva della procedura guidata. Fare clic su **indietro** per apportare modifiche alle pagine precedenti.
    
    <div>
    

    > [!TIP]  
    > Ogni pagina contiene una descrizione dei criteri di selezione e suggerimenti basati sulle procedure preferite e sulla pianificazione della capacità. Se sono necessari altri dettagli, fare clic su <STRONG>altre</STRONG> informazioni per leggere le istruzioni dettagliate della documentazione relativa alla pianificazione di Lync Server 2013 nel sito Web Microsoft TechNet. Per accedere al sito Web Microsoft TechNet è necessario disporre della connettività Internet.

    
    </div>

5.  Selezionare le opzioni appropriate per la progettazione. Dopo aver definito i criteri iniziali, una pagina confermerà che la panoramica delle caratteristiche è completa.

6.  Fare clic su **siti di progettazione** per definire il sito centrale.
    
    <div>
    

    > [!NOTE]  
    > Ogni topologia di Lync Server 2013 avrà almeno un sito centrale. La progettazione può avere un singolo sito centrale, un sito centrale con numerosi siti di succursale, un numero di siti centrali o un numero di siti centrali con siti di succursale associati a ogni sito centrale.

    
    </div>

7.  In **nome sito**Digitare il nome che identificherà questo sito centrale.

8.  Negli **utenti**ospitati nel sito digitare il numero previsto di utenti simultanei locali che verranno assegnati in questo sito centrale.

9.  Negli **utenti cloud homed**Digitare il numero previsto di utenti concorrenti online che verranno assegnati in questo sito centrale.

10. Modificare le selezioni per la collaborazione online, gli utenti, la voce, le opzioni di distribuzione aggiuntive o le applicazioni server, se necessario.
    
    <div>
    

    > [!IMPORTANT]  
    > A questo punto della struttura, è possibile selezionare o deselezionare solo le opzioni per la distribuzione. È tuttavia possibile configurare altre opzioni in una fase successiva dello strumento di pianificazione. Esistono anche opzioni che non sono disponibili e non possono essere deselezionate. Inoltre, potrebbe essere necessario cancellare un'opzione per cancellarne un'altra. Se, ad esempio, si deseleziona l'opzione VoIP <STRONG>aziendale</STRONG> in Voice, vengono deselezionate anche le opzioni <STRONG>gruppo risposta</STRONG>, <STRONG>annuncio</STRONG>e <STRONG>parcheggio di chiamata</STRONG> in applicazioni server (tutte caratteristiche di Enterprise Voice).

    
    </div>

11. Dopo aver definito un nome di sito e un numero di utenti, fare clic su **Avanti**.

12. Le pagine seguenti chiedono informazioni sui domini SIP, le impostazioni conferenza, le impostazioni vocali e l'infrastruttura, la messaggistica unificata di Exchange, l'accesso degli utenti esterni, le impostazioni della chat persistente, le impostazioni client, le opzioni di collocazione e i siti di filiale Rispondere a queste domande in base alle esigenze.

13. La domanda finale chiede se si vuole creare un altro sito centrale. Se si seleziona **Sì**, lo strumento di pianificazione torna alla pagina siti centrali. Se si seleziona **No**, fare clic su **Avanti**e quindi su **disegno** per visualizzare la visualizzazione Topologia globale di alto livello.

14. Per visualizzare una topologia esistente, fare clic su **Visualizza**.

15. Fare clic sul file XML che rappresenta la topologia salvata in precedenza e quindi fare clic su **Apri**.

16. Lo strumento di pianificazione Visualizza la pagina della topologia globale. Ora è possibile iniziare a modificare, aggiornare o modificare la topologia usando gli strumenti disponibili nello strumento di pianificazione.

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

