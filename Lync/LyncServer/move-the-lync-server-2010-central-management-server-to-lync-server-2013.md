---
title: Spostare il server di gestione centrale Lync Server 2010 in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29bdf9a5956dfec0dd35703aaf7a7606da63595b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034466"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a>Spostare il server di gestione centrale Lync Server 2010 in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-25_

Dopo aver eseguito la migrazione da Lync Server 2010 a Lync Server 2013, è necessario spostare il server di gestione centrale Lync Server 2010 in Lync Server 2013 front end server o pool, prima di poter rimuovere il server Lync Server 2010 legacy.

Il server di gestione centrale è un singolo sistema di replica master/multiple, in cui la copia di lettura/scrittura del database è conservata dal front end server che contiene il server di gestione centrale. Ogni computer della topologia, incluso il front end server che contiene il server di gestione centrale, dispone di una copia di sola lettura dei dati dell'archivio di gestione centrale nel database di SQL Server, denominata RTCLOCAL per impostazione predefinita, installata nel computer durante l'installazione e distribuzione. Il database locale riceve gli aggiornamenti delle repliche tramite l'agente Replicator di replica di Lync Server eseguito come servizio in tutti i computer. Il nome del database effettivo sul server di gestione centrale e la replica locale è XDS, costituito dai file XDS. mdf e XDS. ldf. Il percorso del database master è fatto riferimento da un punto di controllo del servizio (SCP) in servizi di dominio Active Directory. Tutti gli strumenti che utilizzano il server di gestione centrale per la gestione e la configurazione di Lync Server utilizzano l'SCP per individuare l'archivio di gestione centrale.

Dopo aver correttamente spostato il server di gestione centrale, è necessario rimuovere i database del server di gestione centrale dal front end server originale. Per informazioni sulla rimozione dei database del server di gestione centrale, vedere [rimuovere il database di SQL Server per un pool Front End](remove-the-sql-server-database-for-a-front-end-pool.md).

Utilizzare il cmdlet **Move-csmanagementserver** di Windows PowerShell in Lync Server Management Shell per spostare il database dal database di SQL Server lync Server 2010 al database di SQL Server di lync Server 2013 e quindi aggiornare il punto SCP in modo che punti al percorso del server di gestione centrale di lync Server 2013.

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a>Preparazione dei front end server di Lync Server 2013 prima dello spostamento del server di gestione centrale

Utilizzare le procedure descritte in questa sezione per preparare i server front end di Lync Server 2013 prima di spostare il server di gestione centrale Lync Server 2010.

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Per preparare un pool Enterprise Edition front end

1.  Nel pool Lync Server 2013 Enterprise Edition front end in cui si desidera spostare il server di gestione centrale, eseguire l'accesso al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** . È inoltre necessario disporre di autorizzazioni e diritti utente del database di SQL Server per il database in cui si desidera installare l'archivio di gestione centrale.

2.  Aprire Lync Server Management Shell.

3.  Per creare il nuovo archivio di gestione centrale nel database di SQL Server Lync Server 2013, in Lync Server Management Shell digitare quanto segue:
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  Verificare che lo stato del servizio **Lync Server Front-End** sia **Avviato**.

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a>Per preparare un front end server Standard Edition

1.  Nel server Lync Server 2013 Standard Edition front end in cui si desidera spostare il server di gestione centrale, eseguire l'accesso al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .

2.  Aprire la Distribuzione guidata di Lync Server.

3.  Nella distribuzione guidata di Lync Server, fare clic su **prepara primo server Standard Edition**.

4.  Nella pagina **esecuzione comandi** in corso, SQL Server Express è installato come server di gestione centrale. Vengono create le regole firewall necessarie. Al termine dell'installazione del database e dei prerequisiti software, fare clic su **Fine**.
    
    <div>
    

    > [!NOTE]  
    > L'installazione iniziale può richiedere tempo senza che vengano visualizzati aggiornamenti visibili nella schermata riepilogativa di output dei comandi. Ciò è dovuto all'installazione di SQL Server Express. Se si desidera monitorare l'installazione del database, usare Gestione attività.

    
    </div>

5.  Per creare il nuovo archivio di gestione centrale in Lync Server 2013 Standard Edition Front End Server, in Lync Server Management Shell digitare quanto segue:
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  Verificare che lo stato del servizio **Lync Server Front-End** sia **Avviato**.

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a>Per spostare il server di gestione centrale Lync Server 2010 in Lync Server 2013

1.  Sul server Lync Server 2013 che fungerà da server di gestione centrale: eseguire l'accesso al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** . È anche necessario disporre dei diritti e delle autorizzazioni di amministratore del database SQL Server.

2.  Aprire Lync Server Management Shell.

3.  In Lync Server Management Shell, digitare quanto segue:
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > Se <CODE>Enable-CsTopology</CODE> l'operazione non è riuscita, risolvere il problema impedendo il completamento del comando prima di continuare. Se <STRONG>Enable-CsTopology</STRONG> non ha esito positivo, lo spostamento avrà esito negativo e potrebbe lasciare la topologia in uno stato in cui non è presente un archivio di gestione centrale.

    
    </div>

4.  Nel server Lync Server 2013 front end o nel pool Front End, in Lync Server Management Shell, digitare quanto segue:
    
        Move-CsManagementServer

5.  Lync Server Management Shell consente di visualizzare i server, i file Store, gli archivi di database e i punti di connessione del servizio dello stato corrente e dello stato proposto. Leggere attentamente le informazioni e verificare che l'origine e la destinazione siano corrette. Digitare **S** per continuare o **N** per interrompere lo spostamento.

6.  Esaminare eventuali avvisi o errori generati dal comando **Move-CsManagementServer** e risolverli.

7.  Nel server Lync Server 2013 aprire la distribuzione guidata di Lync Server.

8.  Nella distribuzione guidata di Lync Server, fare clic su **Installa o aggiorna il sistema Lync Server**, fare clic su **passaggio 2: installazione o rimozione componenti di Lync Server**, fare clic su **Avanti**, esaminare il riepilogo e quindi fare clic su **fine**.

9.  Nel server Lync Server 2010 aprire la distribuzione guidata di Lync Server.

10. Nella distribuzione guidata di Lync Server, fare clic su **Installa o aggiorna il sistema Lync Server**, fare clic su **passaggio 2: installazione o rimozione componenti di Lync Server**, fare clic su **Avanti**, esaminare il riepilogo e quindi fare clic su **fine**.

11. Riavviare il server Lync Server 2013. Questa operazione è necessaria a causa di una modifica dell'appartenenza a un gruppo al database del server di gestione centrale di Access.

12. Per verificare che la replica con il nuovo archivio di gestione centrale si verifichi, in Lync Server Management Shell digitare quanto segue:
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > Il processo di replica può richiedere tempo per aggiornare tutte le repliche correnti.

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a>Per rimuovere i file dell'archivio di gestione centrale di Lync Server 2010 dopo uno spostamento

1.  Nel server Lync Server 2010: accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** . È anche necessario disporre dei diritti e delle autorizzazioni di amministratore del database SQL Server.

2.  Aprire Lync Server Management Shell
    
    <div>
    

    > [!WARNING]  
    > Non procedere con la rimozione dei file di database precedenti prima del completamento e della stabilizzazione della replica. Se si rimuovono i file prima del completamento della replica, si interrompe il processo di replica e si lascia il server di gestione centrale appena spostato in uno stato sconosciuto. Usare il cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> per verificare lo stato della replica.

    
    </div>

3.  Per rimuovere i file di database dell'archivio di gestione centrale dal server di gestione centrale Lync Server 2010, digitare quanto segue:
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    Ad esempio:
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    Dove il \<nome di dominio completo\> di SQL Server è il server di back-end Lync Server 2010 in una distribuzione Enterprise Edition o il nome di dominio completo del server Standard Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

