---
title: Trasferire il server di gestione centrale di Lync Server 2010 in Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abcb361beb82b98cd765b3797b63b22c280fdf70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a>Trasferire il server di gestione centrale di Lync Server 2010 in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-25_

Dopo aver eseguito la migrazione da Lync Server 2010 a Lync Server 2013, è necessario trasferire il server di gestione centralizzato di Lync Server 2010 in Lync Server 2013 front end server o pool, prima di poter rimuovere il server legacy di Lync Server 2010.

Il server di gestione centrale è un singolo sistema master/replica multipla, in cui la copia di lettura/scrittura del database è tenuta dal server front-end che contiene il server di gestione centrale. Ogni computer della topologia, incluso il front end server che contiene il server di gestione centrale, ha una copia di sola lettura dei dati di Central Management store nel database di SQL Server (denominata RTCLOCAL per impostazione predefinita) installati nel computer durante l'installazione e distribuzione. Il database locale riceve gli aggiornamenti della replica tramite l'agente replicatore di Lync Server che viene eseguito come servizio in tutti i computer. Il nome del database effettivo nel server di gestione centrale e la replica locale è XDS, costituito dai file XDS. mdf e XDS. ldf. Il percorso del database master viene fatto riferimento da un punto di controllo del servizio (SCP) in servizi di dominio Active Directory. Tutti gli strumenti che usano il server di gestione centralizzato per gestire e configurare Lync Server usano l'SCP per individuare l'Central Management store.

Dopo aver spostato correttamente il server di gestione centrale, è necessario rimuovere i database di Central Management Server dal server front-end originale. Per informazioni sulla rimozione dei database di Central Management Server, vedere [rimuovere il database di SQL Server per un pool Front-End](remove-the-sql-server-database-for-a-front-end-pool.md).

Puoi usare il cmdlet **Move-csmanagementserver** di Windows PowerShell in Lync Server Management Shell per spostare il database dal database di SQL Server di lync Server 2010 al database di SQL Server di lync Server 2013 e quindi aggiornare il SCP in modo che punti al percorso del server di gestione centrale di lync Server 2013.

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a>Preparazione dei server front-end di Lync Server 2013 prima di spostare il server di gestione centrale

Usare le procedure descritte in questa sezione per preparare i server front end di Lync Server 2013 prima di trasferire il server di gestione centralizzato di Lync Server 2010.

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Per preparare un pool di front-end Enterprise Edition

1.  Nel pool di front end di Lync Server 2013 Enterprise Edition in cui si vuole spostare il server di gestione centralizzato: accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** . Per il database in cui si vuole installare l'Central Management store, è necessario disporre anche dei diritti utente e delle autorizzazioni di amministratore del database di SQL Server.

2.  Aprire Lync Server Management Shell.

3.  Per creare il nuovo archivio di gestione centrale nel database di SQL Server di Lync Server 2013, in Lync Server Management Shell digitare:
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  Verificare che lo stato del servizio **front-end di Lync Server** sia stato **avviato**.

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a>Per preparare un server front-end Standard Edition

1.  Nel server front-end Standard Edition di Lync Server 2013 in cui si vuole spostare il server di gestione centralizzato: accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** .

2.  Aprire la distribuzione guidata di Lync Server.

3.  Nella distribuzione guidata di Lync Server fare clic su **prepara primo server Standard Edition**.

4.  Nella pagina **esecuzione dei comandi** , SQL Server Express viene installato come server di gestione centrale. Vengono create le regole firewall necessarie. Dopo aver completato l'installazione del database e del software prerequisito, fare clic su **fine**.
    
    <div>
    

    > [!NOTE]  
    > L'installazione iniziale può richiedere del tempo senza aggiornamenti visibili alla schermata di riepilogo dell'output del comando. Ciò è dovuto all'installazione di SQL Server Express. Se è necessario monitorare l'installazione del database, usare Gestione attività per monitorare la configurazione.

    
    </div>

5.  Per creare il nuovo archivio di gestione centrale nel server front-end Standard Edition di Lync Server 2013, in Lync Server Management Shell digitare:
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  Verificare che lo stato del servizio **front-end di Lync Server** sia stato **avviato**.

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a>Per trasferire il server di gestione centrale di Lync Server 2010 in Lync Server 2013

1.  Nel server Lync Server 2013 che sarà il server di gestione centralizzato: accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** . È inoltre necessario disporre dei diritti e delle autorizzazioni per gli utenti di amministratore del database di SQL Server.

2.  Aprire Lync Server Management Shell.

3.  In Lync Server Management Shell digitare:
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > Se <CODE>Enable-CsTopology</CODE> l'operazione non riesce, risolvere il problema impedendo il completamento del comando prima di continuare. Se <STRONG>Enable-CsTopology</STRONG> non riesce, il passaggio non riesce e può lasciare la topologia in uno stato in cui non è presente un Central Management store.

    
    </div>

4.  Nel server front-end o nel pool Front-End di Lync Server 2013, in Lync Server Management Shell, digitare:
    
        Move-CsManagementServer

5.  Lync Server Management Shell Visualizza i server, i file Store, gli archivi di database e i punti di connessione del servizio dello stato corrente e dello stato proposto. Leggere attentamente le informazioni e verificare che si tratta dell'origine e della destinazione desiderate. Digitare **Y** per continuare o **N** per interrompere lo stato di trasferimento.

6.  Esaminare gli avvisi o gli errori generati dal comando **Move-csmanagementserver** e risolverli.

7.  Nel server Lync Server 2013 aprire la distribuzione guidata di Lync Server.

8.  Nella distribuzione guidata di Lync Server fare clic su **Installa o aggiorna Lync Server System**, fare clic su **passaggio 2: configurare o rimuovere i componenti di Lync Server**, fare clic su **Avanti**, rivedere il riepilogo e quindi fare clic su **fine**.

9.  Nel server Lync Server 2010 aprire la distribuzione guidata di Lync Server.

10. Nella distribuzione guidata di Lync Server fare clic su **Installa o aggiorna Lync Server System**, fare clic su **passaggio 2: configurare o rimuovere i componenti di Lync Server**, fare clic su **Avanti**, rivedere il riepilogo e quindi fare clic su **fine**.

11. Riavviare il server Lync Server 2013. Questa operazione è necessaria a causa di una modifica dell'appartenenza al gruppo per accedere al database di Central Management Server.

12. Per verificare che la replica con il nuovo archivio di gestione centrale si verifichi, in Lync Server Management Shell digitare:
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > La replica può richiedere del tempo per aggiornare tutte le repliche correnti.

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a>Per rimuovere i file di Lync Server 2010 Central Management store dopo una mossa

1.  Nel server Lync Server 2010: accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo **RTCUniversalServerAdmins** . È inoltre necessario disporre dei diritti e delle autorizzazioni per gli utenti di amministratore del database di SQL Server.

2.  Aprire Lync Server Management Shell
    
    <div>
    

    > [!WARNING]  
    > Non procedere con la rimozione dei file di database precedenti finché la replica non è completa ed è stabile. Se si rimuovono i file prima di completare la replica, si interromperà il processo di replica e si lascerà il server di gestione centralizzato appena spostato in uno stato sconosciuto. Usa il cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> per confermare lo stato di replica.

    
    </div>

3.  Per rimuovere i file di database di Central Management Store dal server di gestione centrale di Lync Server 2010, digitare:
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    Ad esempio:
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    Dove il \<nome di dominio completo\> di SQL Server è il server back-End di Lync Server 2010 in una distribuzione di Enterprise Edition o il nome di dominio completo del server Standard Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

