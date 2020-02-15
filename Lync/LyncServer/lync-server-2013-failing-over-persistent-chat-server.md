---
title: 'Lync Server 2013: failover del server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0d5ac758c1e4c87fd5559da1c2a9cf388dc8834
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a>Failover del server Chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-05_

Il failover per il server Chat persistente è stato creato principalmente come processo manuale.

La procedura di failover si basa sul presupposto che il data center secondario sia attivo e in esecuzione, ma i servizi del server Chat persistente in cui si trova il database di Persistent Chat primario sono completamente non disponibili, inclusi i seguenti:

  - Database primario del server Chat persistente e database mirror del server Chat persistente sono indesiderati.

  - Lync Server front end server è inverso.

La procedura prevede due passaggi di base:

  - Ripristinare il database di Persistent Chat principale (MGC).

  - Configurazione del mirroring per il nuovo database primario.

Non è stato eseguito il failover del database di conformità di Persistent Chat (mgccomp). Il contenuto di questo database è temporaneo e viene eliminato durante l'elaborazione dei dati nell'adattatore di conformità. La responsabilità, come amministratore di chat persistente, è quella di gestire correttamente l'output dell'adattatore per evitare la perdita di dati.

<div>

## <a name="to-fail-over-persistent-chat-server"></a>Per eseguire il failover del server Chat persistente

1.  Rimuovere il log shipping dal database del log shipping del server di backup di Persistent Chat.
    
    1.  Tramite SQL Server Management Studio connettersi all'istanza del database in cui si trova il database di backup di MGC del server Chat persistente.
    
    2.  Aprire una finestra di query nel database master.
    
    3.  Usare questo comando per eliminare la distribuzione dei log:
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  Copiare i file di backup non copiati dalla condivisione di backup nella cartella di destinazione della copia del server di backup.

3.  Applicare i backup dei log delle transazioni non applicati in sequenza al database secondario. Per informazioni dettagliate, vedere "How to: Apply a Transaction log backup (Transact-SQL)" http://go.microsoft.com/fwlink/p/?linkid=247428at.

4.  Connettere il database mgc di backup. Usando la finestra di query aperta al passaggio 1b, eseguire le operazioni seguenti:
    
    1.  Terminare tutte le connessioni al database mgc, se disponibili:
        
        1.  **Exec SP\_who2** per identificare le connessioni al database di MGC.
        
        2.  **Kill \<SPID\> ** per terminare queste connessioni.
    
    2.  Connettere il database:
        
        1.  **ripristinare i database di MGC con il ripristino**.

5.  In Lync Server Management Shell, utilizzare il comando **Set-CsPersistentChatState-Identity "Service: atl-cs-001.litwareinc.com" – PoolState FailedOver** per eseguire il failover nel database di backup di MGC. Assicurarsi di sostituire il nome di dominio completo del pool di Persistent Chat per atl-cs-001.litwareinc.com.
    
    Il database mgc di backup funge ora da database primario.

6.  In Lync Server Management Shell, utilizzare il cmdlet **Install-CsMirrorDatabase** per definire un mirror a disponibilità elevata per il database di backup che ora funge da database primario. Usare l'istanza del database di backup come database primario e l'istanza del database mirror di backup come istanza mirror. Questo mirror non corrisponde al mirror configurato inizialmente per il database primario durante l'installazione. Per informazioni dettagliate, vedere la sezione "utilizzo dei cmdlet di Lync Server Management Shell" nella [distribuzione del mirroring SQL per la disponibilità elevata del server back-end in Lync server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

7.  Impostare i server attivi del server Chat persistente. Dalla shell dei comandi di Lync Server, utilizzare il cmdlet **Set-CsPersistentChatActiveServer** per impostare l'elenco di server attivi.
    
    <div>
    

    > [!IMPORTANT]  
    > Tutti i server attivi devono trovarsi all'interno dello stesso data center del nuovo database primario o in un data center con una connessione a bassa latenza/larghezza di banda elevata al database.

    
    </div>
    
    A questo punto, il failover dal database primario del server Chat persistente al database di backup del server Chat persistente è stato completato correttamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

