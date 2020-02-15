---
title: 'Lync Server 2013: failover del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7a0e7bef65773c20c5d97a1b625d2ef39255f64
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a>Failover del server Chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-05_

In questa procedura vengono illustrati i passaggi necessari per eseguire il ripristino da un errore del server Chat persistente e per ristabilire le operazioni dal data center principale.

Durante l'errore del server Chat persistente, il data center principale soffre di un'interruzione completa e i database primario e mirror diventano non disponibili. Il centro dati principale esegue il failover al server di backup.

La procedura seguente consente di ripristinare l'operatività normale dopo il backup del centro dati principale e la ricostruzione dei server. La procedura presuppone che il data center principale sia stato recuperato dall'interruzione totale e che il database di MGC e il database di mgccomp siano stati ricompilati e reinstallati tramite Generatore di topologie.

La procedura presuppone inoltre che nessun nuovo mirror e server di backup siano stati distribuiti durante il periodo di failover e che il solo server distribuito sia il server di backup e il server mirror, come definito in [failover del server Chat persistente in Lync server 2013](lync-server-2013-failing-over-persistent-chat-server.md).

Questi passaggi sono pensati per consentite il ripristino della configurazione esistente prima della situazione di emergenza che ha causato il failover dal server primario a quello di backup.

<div>

## <a name="to-fail-back-persistent-chat-server"></a>Per eseguire il failover del server Chat persistente

1.  Cancellare tutti i server dall'elenco Active server Chat persistente utilizzando il `Set-CsPersistentChatActiveServer` cmdlet di Lync Server Management Shell. In questo modo tutti i server di chat persistente si connettono al database di MGC e al database di mgccomp durante il failback.
    
    <div>
    

    > [!IMPORTANT]  
    > Il server SQL Server Agent sul server back-end di chat persistente secondario dovrebbe essere in esecuzione con un account con privilegi. In particolare, l'account deve disporre di: 
    > <UL>
    > <LI>
    > <P>Accesso in lettura alla condivisione di rete in cui vengono posizionati i backup.</P>
    > <LI>
    > <P>Accesso in scrittura alla directory locale specifica in cui vengono copiati i backup.</P></LI></UL>

    
    </div>

2.  Disabilitare il mirroring nel database mgc di backup:
    
    1.  Tramite SQL Server Management Studio connettersi all'istanza di backup di MGC.
    
    2.  Fare clic con il pulsante destro del mouse sul database mgc, scegliere **Attività** e quindi fare clic su **Server mirror**.
    
    3.  Fare clic su **Rimuovi mirroring**.
    
    4.  Fare clic su **OK**.
    
    5.  Eseguire gli stessi passaggi con il database mgccomp.

3.  Eseguire il backup del database mgc in modo che possa essere ripristinato nel nuovo database primario:
    
    1.  Tramite SQL Server Management Studio connettersi all'istanza di backup di MGC.
    
    2.  Fare clic con il pulsante destro del mouse sul database mgc, scegliere **Attività** e quindi fare clic su **Backup**. Verrà visualizzata la finestra di dialogo **Backup database**.
    
    3.  In **Tipo backup** selezionare **Completo**.
    
    4.  In **Componente di cui eseguire il backup** fare clic su **Database**.
    
    5.  Accettare il nome del set di backup predefinito indicato in **Nome** oppure immettere un nome diverso per il set di backup.
    
    6.  * \<Facoltativo\> * In **Descrizione**immettere una descrizione del set di backup.
    
    7.  Rimuovere il percorso di backup predefinito dall'elenco di destinazione.
    
    8.  Aggiungere un file all'elenco utilizzando il percorso della posizione condivisa stabilita per il log shipping. Questo percorso è disponibile per il database primario e quello di backup.
    
    9.  Fare clic su **OK** per chiudere la finestra di dialogo e avviare il processo di backup.

4.  Ripristinare il database primario utilizzando il database di backup creato nel passaggio precedente.
    
    1.  Tramite SQL Server Management Studio connettersi all'istanza di MGC principale.
    
    2.  Fare clic con il pulsante destro del mouse sul database mgc, scegliere **Attività**, **Ripristina** e quindi fare clic su **Database**. Verrà visualizzata la finestra di dialogo **Ripristina database**.
    
    3.  Selezionare **Dispositivo di origine**.
    
    4.  Fare clic sul pulsante Sfoglia per aprire la finestra di dialogo **Seleziona backup**. In **Supporti di backup** selezionare **File**. Fare clic su **Aggiungi**, selezionare il file di backup creato nel passaggio 3 e quindi fare clic su **OK**.
    
    5.  In **Selezionare i set di backup da ripristinare** selezionare il backup.
    
    6.  Fare clic su **Opzioni** nel riquadro **Selezione pagina**.
    
    7.  In **Opzioni di ripristino** selezionare **Sovrascrivi il database esistente **.
    
    8.  In **Stato di recupero** selezionare **Lascia il database pronto per l'utilizzo**.
    
    9.  Fare clic su **OK** per avviare il processo di ripristino.

5.  Configurare il log shipping di SQL Server per il database primario. Seguire le procedure riportate in [configurazione del server Chat persistente per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) per stabilire il log shipping per il database di MGC primario.

6.  Impostare i server attivi del server Chat persistente. Da Lync Server Management Shell, utilizzare il cmdlet **Set-CsPersistentChatActiveServer** per impostare l'elenco dei server attivi.
    
    <div>
    

    > [!IMPORTANT]  
    > Tutti i server attivi devono trovarsi all'interno dello stesso data center del nuovo database primario o in un data center con una connessione a bassa latenza/larghezza di banda elevata al database.

    
    </div>

Il ripristino del pool allo stato normale viene eseguito il comando di Windows PowerShell seguente:

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

