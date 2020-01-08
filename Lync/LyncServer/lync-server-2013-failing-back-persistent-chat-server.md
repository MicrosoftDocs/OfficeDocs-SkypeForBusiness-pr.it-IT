---
title: 'Lync Server 2013: Failback del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d79c25d153de81906fcaf9355a543d31cb8fe0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a>Failback del server Chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-05_

Questa procedura descrive i passaggi necessari per il ripristino da un errore del server di chat persistente e per ristabilire le operazioni dal centro dati principale.

Durante l'errore del server di chat persistente, il centro dati principale soffre l'interruzione completa e i database primari e mirror diventano non disponibili. Il data center principale viene superato nel server di backup.

La procedura seguente ripristina il normale funzionamento dopo il backup del data center principale e i server sono stati ricompilati. La procedura presuppone che il centro dati principale sia stato recuperato dall'interruzione totale e che il database di MGC e il database di mgccomp siano stati ricostruiti e reinstallati usando generatore di topologie.

La procedura presuppone inoltre che non siano stati distribuiti nuovi mirror e server di backup durante il periodo di failover e che l'unico server distribuito sia il server di backup e il relativo server mirror, come definito in mancanza di un [server di chat persistente in Lync server 2013](lync-server-2013-failing-over-persistent-chat-server.md).

Questi passaggi sono progettati per recuperare la configurazione come esisteva prima del disastro, causando il failover dal server primario al server di backup.

<div>

## <a name="to-fail-back-persistent-chat-server"></a>Per non ripristinare il server di chat persistente

1.  Cancellare tutti i server dall'elenco Active server Chat persistente usando il `Set-CsPersistentChatActiveServer` cmdlet di Lync Server Management Shell. In questo articolo vengono arrestati tutti i server di chat persistenti che si connettono al database mgc e mgccomp durante il failback.
    
    <div>
    

    > [!IMPORTANT]  
    > L'agente SQL Server nel server di chat secondario persistente deve essere in uso in un account con privilegi. In particolare, l'account deve includere: 
    > <UL>
    > <LI>
    > <P>Accesso in lettura alla condivisione di rete in cui vengono inseriti i backup.</P>
    > <LI>
    > <P>Accesso in scrittura alla directory locale specifica in cui vengono copiati i backup.</P></LI></UL>

    
    </div>

2.  Disabilitare il mirroring nel database di backup MGC:
    
    1.  Con SQL Server Management Studio connettersi all'istanza di backup MGC.
    
    2.  Fare clic con il pulsante destro del mouse sul database di MGC, scegliere **attività**e quindi fare clic su **Specchia**.
    
    3.  Fare clic su **Rimuovi mirroring**.
    
    4.  Fare clic su **OK**.
    
    5.  Eseguire gli stessi passaggi con il database mgccomp.

3.  Eseguire il backup del database di MGC in modo che possa essere ripristinato nel nuovo database primario:
    
    1.  Con SQL Server Management Studio connettersi all'istanza di backup MGC.
    
    2.  Fare clic con il pulsante destro del mouse sul database di MGC, scegliere **attività**e quindi fare clic su **backup**. Verrà visualizzata la finestra di dialogo **backup database** .
    
    3.  In **tipo di backup**selezionare **completo**.
    
    4.  Per il **componente backup**fare clic su **database**.
    
    5.  Accettare il nome predefinito del set di backup consigliato in **nome**o immettere un nome diverso per il set di backup.
    
    6.  * \<Facoltativo\> * In **Descrizione**immettere una descrizione del set di backup.
    
    7.  Rimuovere la posizione di backup predefinita dall'elenco di destinazione.
    
    8.  Aggiungere un file all'elenco usando il percorso della posizione di condivisione stabilita per il log shipping. Questo percorso è disponibile per il database principale e per il database di backup.
    
    9.  Fare clic su **OK** per chiudere la finestra di dialogo e avviare il processo di backup.

4.  Ripristinare il database principale usando il database di backup creato nel passaggio precedente.
    
    1.  Con SQL Server Management Studio, connettersi all'istanza di MGC primaria.
    
    2.  Fare clic con il pulsante destro del mouse sul database di MGC, scegliere **attività**, scegliere **Ripristina**e quindi fare clic su **database**. Verrà visualizzata la finestra di dialogo **Ripristina database** .
    
    3.  Selezionare **da dispositivo**.
    
    4.  Fare clic sul pulsante Sfoglia, che apre la finestra di dialogo **specifica backup** . In **supporto di backup**selezionare **file**. Fare clic su **Aggiungi**, selezionare il file di backup creato nel passaggio 3 e quindi fare clic su **OK**.
    
    5.  In **selezionare i set di backup da ripristinare**selezionare il backup.
    
    6.  Fare clic su **Opzioni** nel riquadro **Seleziona pagina** .
    
    7.  In **Opzioni di ripristino**selezionare **sovrascrivere il database esistente**.
    
    8.  In **stato di ripristino**selezionare **lascia il database pronto per l'uso**.
    
    9.  Fare clic su **OK** per avviare il processo di ripristino.

5.  Configurare la distribuzione del log di SQL Server per il database principale. Seguire le procedure descritte in [configurazione del server di chat persistente per l'elevata disponibilità e il ripristino di emergenza in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) per stabilire la distribuzione del log per il database mgc principale.

6.  Impostare i server attivi della chat persistente. Da Lync Server Management Shell utilizzare il cmdlet **Set-CsPersistentChatActiveServer** per impostare l'elenco di server attivi.
    
    <div>
    

    > [!IMPORTANT]  
    > Tutti i server attivi devono essere posizionati all'interno dello stesso centro dati del nuovo database primario o in un centro dati con una connessione a una larghezza di banda ridotta o a un'altezza elevata del database.

    
    </div>

Il comando Ripristina lo stato normale del pool viene eseguito in Windows PowerShell seguente:

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

