---
title: 'Lync Server 2013: associazione di un archivio di monitoraggio con un pool Front-End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associating a monitoring store with a Front End pool
ms:assetid: d3a20d5e-3f24-4cff-bc9b-4f84fea30e6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205271(v=OCS.15)
ms:contentKeyID: 48185439
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c1153d0d20cf5a3855a36f8d7aa24a8d9d4680b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-a-monitoring-store-with-a-front-end-pool-in-lync-server-2013"></a>Associazione di un archivio di monitoraggio con un pool Front-end in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-04-22_

In Microsoft Lync Server 2013 i dati di monitoraggio possono essere raccolti solo nei pool Front-End associati a un archivio di monitoraggio, un'attività eseguita in genere per definire un pool Front end in Generatore di topologie. Per associare un archivio di monitoraggio a un nuovo pool Front-End, verificare di aver selezionato il **monitoraggio delle opzioni (registrazione dei dettagli delle chiamate e registrazione delle metriche di qualità delle esperienze)** nella pagina **selezionare le caratteristiche** della procedura guidata per definire il nuovo pool Front-end. Si noti che, se si seleziona questa opzione, è necessario specificare anche un archivio SQL per completare la procedura guidata. Tuttavia, questo archivio non deve esistere quando si esegue la procedura guidata. Questo significa che puoi prima associare un pool a un archivio di monitoraggio, quindi installarlo e configurarlo in seguito.

In alternativa, è possibile associare un pool Front end esistente a un archivio di monitoraggio nuovo o diverso completando la procedura seguente:

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

2.  Nella finestra di dialogo **Generatore di topologia** selezionare **Scarica topologia da distribuzione esistente** e quindi fare clic su **OK**.

3.  Nella finestra di dialogo **Salva con** nome immettere un file per la topologia corrente e quindi fare clic su **Salva**. La topologia salvata può in seguito essere recuperata e ripubblicata in caso di problemi con la nuova topologia.

4.  In Generatore di topologie espandere **Lync Server 2013**, espandere il nome del sito contenente il pool Front-End, quindi fare clic su Espandi **pool di front-end Enterprise Edition**.

5.  Fare clic con il pulsante destro del mouse sul nome del pool da associare all'archivio di monitoraggio e quindi scegliere **modifica proprietà**.

6.  Nella scheda **generale** della finestra di dialogo **modifica proprietà** selezionare l'opzione **monitoraggio (CdR e QoE Metrics)** e quindi selezionare un database di SQL Server esistente nell'elenco a discesa **monitoraggio di SQL Server Store** . In alternativa, fare clic su **nuovo** per associare il pool a un nuovo archivio di database. Se si sceglie di usare un nuovo archivio di database, nella finestra di dialogo **Definisci nuovo archivio SQL** immettere il nome di dominio completo del computer SQL Server nella casella **FQDN di SQL Server** . Se si vuole usare l'istanza predefinita di SQL Server per lo Store, selezionare **istanza predefinita**. in caso contrario, seleziona **istanza denominata** e immetti il nome dell'istanza nella casella **istanza denominata** .
    
    La finestra di dialogo **modifica proprietà** offre anche la possibilità di creare un mirror SQL per il database di monitoraggio (un mirror SQL consente di gestire due copie del database di monitoraggio, una copia archiviata nel computer dell'archivio di monitoraggio e l'altra nel computer SQL mirror). Per abilitare il mirroring, selezionare T**la relativa istanza SQL è in relazione di mirroring** e immettere il numero di porta per il server mirror nella casella **numero porta di mirroring** .

7.  Nella finestra di dialogo **modifica proprietà** fare clic su **OK**.

Dopo aver associato l'archivio di monitoraggio con un pool Front-End, è necessario pubblicare la nuova topologia prima che le modifiche abbiano effetto. Per pubblicare la nuova topologia, completare i passaggi seguenti in Generatore di topologie:

1.  Fare clic su **azione**, scegliere **topologia**e quindi fare clic su **pubblica**.

2.  Nella pagina **Pubblica topologia** della procedura guidata Pubblica topologia fare clic su **Avanti**.

3.  Nella pagina **completamento pubblicazione guidata** fare clic su **fine**.

Una volta pubblicata la topologia, è possibile installare il database di monitoraggio nel computer che ospiterà l'archivio di monitoraggio. Il database di monitoraggio può essere installato tramite Lync Server Management Shell e Windows PowerShell. Per installare il database in locale, ovvero per installare il database nello stesso computer in cui è in uso Lync Server Management Shell, avviare Gestione Shell nel computer appropriato, quindi digitare il comando seguente e premere INVIO:

    Install-CsDatabase -LocalDatabases

Quando si esegue il comando precedente, Install-CsDatabase leggerà la topologia di Lync Server corrente, determina quali database devono essere installati nel computer locale e quindi installa e configura automaticamente ognuno di questi database.

Per installare il database in un computer remoto, ovvero un computer diverso dal computer in cui è in uso la shell di gestione, è necessario includere almeno due parametri: il parametro ConfiguredDatabases e il parametro SqlServerFqdn. Questi parametri indicano al cmdlet Install-CsDatabase di recuperare la topologia di Lync Server e quindi installare e configurare i database necessari nel computer specificato dal parametro SqlServerFqdn. Il parametro SqlServerFqdn deve usare un valore di parametro che rappresenta il nome di dominio completo del computer in cui devono essere installati i database.

Questo comando, ad esempio, installa il database di monitoraggio nel computer atl-sql-001.litwareinc.com:

    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn atl-sql-001.litwareinc.com

In alternativa, è possibile installare il database di monitoraggio eseguendo la distribuzione guidata di Lync Server nel computer che ospiterà l'archivio di monitoraggio. A questo scopo, accedere al computer appropriato e completare la procedura seguente:

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **distribuzione guidata Lync Server**.

2.  Nella distribuzione guidata fare clic su **Installa o aggiorna Lync Server System**.

3.  Nella pagina **Distribuisci** , in **passaggio 2: configurare o rimuovere componenti di Lync Server**, fare di nuovo clic su **Esegui**.

4.  Nella pagina Setup Lync Server Components, nella pagina **configurazione dei componenti di Lync Server** , fare clic su **Avanti**.

5.  Nella pagina **specifica il percorso di MSI** Digitare il percorso del file OCSCore. msi (un file incluso nel supporto di installazione di Lync Server) e quindi fare clic su **Avanti**.

6.  Nella pagina **esecuzione dei comandi** fare clic su **fine**.

Per assicurarsi che tutti i servizi di Lync Server necessari siano già stati avviati, fare clic su **Esegui** sotto il titolo **passaggio 4: avviare i servizi** nella pagina **Distribuisci**

</div>

<span> </span>

</div>

</div>

</div>

