---
title: 'Lync Server 2013: Failover del server Chat persistente'
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
ms.openlocfilehash: dd62d4037ae1795a553d207cb698f88f9b3b8ab8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a>Failover del server Chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-05_

Il failover per il server di chat persistente è progettato per essere principalmente un processo manuale.

La procedura di failover si basa sul presupposto che il data center secondario sia attivo e funzionante, ma i servizi di Persistent Chat Server in cui si trova il database principale della chat persistente sono completamente non disponibili, inclusi i seguenti:

  - Il database primario del server Chat persistente e il database mirror del server di chat persistente non sono disponibili.

  - Il server front-end di Lync Server non è più presente.

La procedura si basa su due passaggi di base:

  - Recuperare il database principale della chat persistente (MGC).

  - Stabilire il mirroring per il nuovo database primario.

Il database di conformità della chat persistente (mgccomp) non viene superato. Il contenuto di questo database è temporaneo e viene eliminato quando l'adattatore di conformità elabora i dati. È tua responsabilità, come amministratore della chat persistente, gestire correttamente l'output della scheda per evitare perdite di dati.

<div>

## <a name="to-fail-over-persistent-chat-server"></a>Per eseguire il failover del server di chat persistente

1.  Rimuovere il log shipping dal database di log shipping del server di backup di Persistent Chat.
    
    1.  In SQL Server Management Studio connettersi all'istanza del database in cui si trova il database di backup di MGC del server di chat persistente.
    
    2.  Aprire una finestra di query nel database master.
    
    3.  Usare il comando seguente per eliminare il log shipping:
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  Copiare i file di backup non copiati dalla condivisione di backup alla cartella di destinazione della copia del server di backup.

3.  Applicare i backup del log delle transazioni non applicati in sequenza al database secondario. Per informazioni dettagliate, vedere "procedura: applicare un backup del log delle transazioni (Transact-SQL) http://go.microsoft.com/fwlink/p/?linkid=247428" at.

4.  Porta il database di backup MGC online. Usando la finestra della query visualizzata nel passaggio 1b, eseguire le operazioni seguenti:
    
    1.  Terminare tutte le connessioni al database di MGC, se presenti:
        
        1.  **Exec SP\_who2** per identificare le connessioni al database di MGC.
        
        2.  **uccidere \<SPID\> ** per terminare queste connessioni.
    
    2.  Porta il database online:
        
        1.  **ripristinare il database di MGC con il ripristino**.

5.  In Lync Server Management Shell usare il comando **Set-CsPersistentChatState-Identity "Service: atl-cs-001.litwareinc.com"-PoolState FailedOver** per eseguire il failover nel database di backup di MGC. Assicurarsi di sostituire il nome di dominio completo del pool di chat persistente per atl-cs-001.litwareinc.com.
    
    Il database di backup di MGC ora funge da database primario.

6.  In Lync Server Management Shell usare il cmdlet **Install-CsMirrorDatabase** per stabilire un mirror di disponibilità elevata per il database di backup che ora funge da database primario. Usa l'istanza del database di backup come database principale e l'istanza del database mirror di backup come istanza di mirror. Questo non è lo stesso mirror di quello inizialmente configurato per il database principale durante l'installazione. Per informazioni dettagliate, vedere la sezione "utilizzo dei cmdlet di Lync Server Management Shell" nella [distribuzione di mirroring SQL per l'elevata disponibilità del server back-end in Lync server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

7.  Impostare i server attivi della chat persistente. Nella shell dei comandi di Lync Server usare il cmdlet **Set-CsPersistentChatActiveServer** per impostare l'elenco di server attivi.
    
    <div>
    

    > [!IMPORTANT]  
    > Tutti i server attivi devono essere posizionati all'interno dello stesso centro dati del nuovo database primario o in un centro dati con una connessione a una larghezza di banda ridotta o a un'altezza elevata del database.

    
    </div>
    
    A questo punto, il failover dal database primario del server di chat persistente al database di backup del server di chat persistente viene completato correttamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

