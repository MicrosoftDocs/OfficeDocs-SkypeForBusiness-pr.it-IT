---
title: 'Lync Server 2013: associazione di un archivio di monitoraggio a un pool Front End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfdff8863c0e629c99d0e64aca0b7f84dcb63a43
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a>Associazione di un archivio di monitoraggio a un pool Front end in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-04-22_

In Microsoft Lync Server 2013 i dati di monitoraggio possono essere raccolti solo nei pool Front end che sono stati associati a un archivio di monitoraggio, un'attività in genere eseguita si definisce un pool Front end in Generatore di topologie. Per associare un archivio di monitoraggio a un nuovo pool Front End, è necessario selezionare l'opzione **monitoraggio (registrazione dettagli chiamata e registrazione delle metriche sulla qualità delle esperienze)** nella pagina **Seleziona funzionalità** della procedura guidata Definisci nuovo pool Front end. Si noti che, se si seleziona questa opzione, è necessario specificare anche un archivio SQL per completare la procedura guidata. Tuttavia, questo archivio non deve esistere nel momento in cui viene eseguita la procedura guidata. Questo significa che è possibile associare un pool a un archivio di monitoraggio, quindi installarlo e configurarlo in un secondo momento.

In alternativa, è possibile associare un pool Front End esistente a un archivio di monitoraggio nuovo o diverso eseguendo la procedura seguente:

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**, quindi fare clic su **Generatore di topologie di Lync Server**.

2.  Nella finestra di dialogo **Generatore di topologie** selezionare **Scarica topologia dalla distribuzione esistente** e quindi fare clic su **OK**.

3.  Nella finestra di dialogo **Salva con nome** immettere un nome file per la topologia corrente e quindi fare clic su **Salva**. La topologia salvata può essere successivamente recuperata e ripubblicata in caso di problemi con la nuova topologia.

4.  In Generatore di topologie espandere **Lync Server 2013**, espandere il nome del sito contenente il pool Front end e quindi fare clic su Espandi **pool Enterprise Edition front end**.

5.  Fare clic con il pulsante destro del mouse sul nome del pool da associare all'archivio di monitoraggio e quindi scegliere **Modifica proprietà**.

6.  Nella finestra di dialogo **Modifica proprietà** nella scheda **Generale** selezionare l'opzione **Monitoraggio (registrazione dettagli chiamata e registrazione metrica QoE** e quindi selezionare un database di SQL Server esistente nell'elenco a discesa **Archivio SQL Server monitoraggio**. In alternativa, fare clic su **Nuovo** per associare il pool a un nuovo archivio database. Se si sceglie di utilizzare il nuovo archivio database, nella finestra di dialogo **Definisci nuovo archivio SQL** immettere il nome di dominio completo del computer SQL Server nella casella **FQDN SQL Server**. Se si desidera utilizzare l'istanza di SQL Server predefinita per l'archivio, selezionare **Istanza predefinita**, altrimenti selezionare **Istanza denominata** e immettere il nome dell'istanza nella casella **Istanza denominata**.
    
    La finestra di dialogo **Modifica proprietà** consente inoltre di creare un mirror SQL per il database di monitoraggio. Un mirror SQL consente di mantenere due copie del database di monitoraggio, una archiviata nel computer dell'archivio di monitoraggio e l'altra nel computer mirror SQL. Per abilitare il mirroring, selezionare **L'istanza SQL è in relazione di mirroring** e immettere il numero di porta del server mirror nella casella **Numero porta di mirroring**.

7.  Nella finestra di dialogo **Modifica proprietà** fare clic su **OK**.

Dopo aver associato l'archivio di monitoraggio a un pool Front End, è necessario pubblicare la nuova topologia per rendere effettive le modifiche. A tale scopo, eseguire le operazioni seguenti in Generatore di topologie:

1.  Fare clic su **Azione**, scegliere **Topologia** e quindi **Pubblica**.

2.  Nella pagina **Pubblicare la topologia** della procedura guidata Pubblica topologia fare clic su **Avanti**.

3.  Nella pagina **Pubblicazione guidata completata** fare clic su **Fine**.

Dopo la pubblicazione della topologia, è possibile installare il database di monitoraggio nel computer che ospiterà l'archivio di monitoraggio. È possibile installare il database di monitoraggio utilizzando Lync Server Management Shell e Windows PowerShell. Per installare il database localmente, ovvero per installare il database nello stesso computer in cui è in esecuzione Lync Server Management Shell, avviare la shell di gestione nel computer appropriato e quindi digitare il comando seguente e premere INVIO:

    Install-CsDatabase -LocalDatabases

Quando si esegue il comando precedente, Install-CsDatabase legge la topologia di Lync Server corrente, determina quali database devono essere installati nel computer locale e quindi installa e configura automaticamente ognuno di questi database.

Per installare il database in un computer remoto, ovvero un computer diverso da quello in cui è in esecuzione Management Shell, è necessario includere almeno due parametri: ConfiguredDatabases e SqlServerFqdn. Questi parametri indicano al cmdlet Install-CsDatabase di recuperare la topologia di Lync Server e quindi installano e configurano i database necessari nel computer specificato dal parametro SqlServerFqdn. Il parametro SqlServerFqdn deve utilizzare un valore di parametro che rappresenta il nome di dominio completo del computer in cui devono essere installati i database.

Con il comando seguente ad esempio il database di monitoraggio viene installato nel computer atl-sql-001.litwareinc.com:

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

In alternativa, è possibile installare il database di monitoraggio eseguendo la distribuzione guidata di Lync Server nel computer che ospiterà l'archivio di monitoraggio. A tale scopo, accedere al computer appropriato ed eseguire la procedura seguente:

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi **distribuzione guidata di Lync Server**.

2.  Nella Distribuzione guidata fare clic su **Installa o aggiorna il sistema Lync Server**.

3.  In **Passaggio 2: Installazione o rimozione componenti di Lync Server** nella pagina **Distribuisci** fare clic su **Riesegui**.

4.  Nella pagina **Installazione componenti di Lync Server** della procedura guidata Installazione componenti di Lync Server fare clic su **Avanti**.

5.  Nella pagina **Specifica percorso di MSI** Digitare il percorso del file OCSCore. msi (un file incluso nel supporto di installazione di Lync Server) e quindi fare clic su **Avanti**.

6.  Nella pagina **Esecuzione comandi in corso** fare clic su **Fine**.

Per assicurarsi che tutti i servizi di Lync Server necessari siano stati avviati, fare clic su **Esegui** nell'intestazione **passaggio 4: avviare i servizi** nella pagina **Distribuisci** .

</div>

<span> </span>

</div>

</div>

</div>

