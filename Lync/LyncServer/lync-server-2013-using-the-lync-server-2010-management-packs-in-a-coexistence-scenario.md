---
title: Uso dei Management Pack di Lync Server 2010 in uno scenario di coesistenza
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 264cd8f1495840eb6dd86879f279110cd4de4784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a>Uso dei Management Pack di Lync Server 2010 in uno scenario di coesistenza

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

Molti clienti adottano un programma di implementazione all'interno delle aziende in cui gli utenti vengono progressivamente migrati da Microsoft Lync Server 2010 a Lync Server 2013. Gli amministratori di queste aziende si preoccuperanno del monitoraggio di entrambe le versioni di Lync Server per garantire che tutti gli utenti finali possano ottenere la migliore esperienza di comunicazione. Per questo scenario, il Management Pack di Lync Server 2013 supporta un percorso di migrazione affiancato con Lync Server 2010 Management Pack.

In Lync Server 2010 i computer Lync Server sono stati scoperti tramite il documento di topologia archiviato con l'Central Management store. In questa configurazione un singolo computer segnala l'esistenza di tutti gli altri computer Lync Server.

I Management Pack per Lync Server 2013 ora usano l'individuazione a livello di computer anziché il meccanismo di individuazione centralizzato usato in Lync Server 2010. Questo significa che ogni agente del centro di sistema si rivela essenzialmente e ne segnala l'esistenza a System Center Operations Manager. L'uso dell'individuazione a livello di computer semplifica l'amministrazione dell'infrastruttura del centro di sistema e consente anche versioni diverse di Lync Server Management Pack, ad esempio Management Pack per Lync Server 2010 e Management Pack per Lync Server 2013. per convivere più facilmente.

Per supportare la migrazione, è necessario aggiornare il monitoraggio esistente di Lync Server 2010 per evitare lacune nella copertura. A questo scopo, è necessario eleggere un computer Lync Server 2010 esistente per il servizio dello script di individuazione centralizzato per Lync Server 2010 prima di eseguire l'aggiornamento di Central Management store a Lync Server 2013. Si tratta di un processo in quattro passaggi:

1.  Aggiornare i Management Pack di Lync Server 2010 all'aggiornamento cumulativo 7.

2.  Indicare a un computer Lync Server 2010 di eseguire lo script di individuazione centralizzato.

3.  Eseguire l'override del candidato di individuazione centralizzato nel Management Pack di Microsoft Lync Server 2010.

4.  Verificare che il nuovo candidato di individuazione centrale sia stato individuato.

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a>Istruzione di un computer Lync Server 2010 per l'esecuzione dello script di individuazione centralizzato

Per nominare un computer dell'archivio di gestione non centrale, ad esempio un server front end di Lync Server, per gestire l'individuazione centralizzata, è necessario creare la chiave del registro di sistema seguente nel server dell'archivio di gestione non centrale:

HKLM\\software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate

Per creare questa chiave del registro di sistema, è possibile completare la procedura seguente:

1.  Fare clic sul pulsante **Start** e quindi su **Esegui**.

2.  Nella finestra di dialogo **Esegui** Digitare **Regedit** e quindi premere INVIO.

3.  In Editor del registro di **sistema\_espandere\_HKEY computer locale**, espandere il **software**, espandere **Microsoft**e quindi espandere **comunicazioni in tempo reale**.

4.  Fare clic con il pulsante destro del mouse su **integrità**, scegliere **nuovo**e quindi fare clic su **chiave**. Se il codice di **integrità** non esiste, fare clic con il pulsante destro del mouse su **comunicazioni in tempo reale**, scegliere **nuovo**e quindi fare clic su **chiave**. Quando viene creata la nuova chiave, digitare integrità e quindi premere INVIO.
    
    Dopo aver creato la nuova chiave, digitare **CentralDiscoveryCandidate** e quindi premere INVIO per rinominare la chiave.

Il computer può richiedere diverse ore per raccogliere la modifica. Per rendere effettive le modifiche, interrompere e riavviare il servizio agente di integrità. Per riavviare il servizio Agente integrità, eseguire la procedura seguente nel computer Lync Server 2010:

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Accessori**, fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.

2.  Nella finestra della console digitare il comando seguente e quindi premere INVIO:
    
        Net stop HealthService

3.  Verrà visualizzato un messaggio che indica che "il servizio di gestione del centro di sistema si arresta", seguito da un secondo messaggio che informa che il servizio è stato interrotto. Dopo l'interruzione del servizio, è possibile riavviarlo digitando il comando seguente e premendo INVIO:
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a>Override del candidato di individuazione centralizzato nel Management Pack di Lync Server 2010

Dopo aver indicato a un computer Lync Server 2010 di segnalare i computer di Lync Server 2010, è necessario informare anche il Management Pack di Lync Server 2010. A tale scopo, è necessario creare un override nel Management Pack. Questa operazione può essere eseguita completando la procedura seguente:

1.  Nella console di Operations Manager fare clic su **creazione**.

2.  Nella scheda Creazione espandere **oggetti Management Pack**, fare clic su **individuazioni**oggetti e quindi fare clic su **ambito**.

3.  Nella finestra di dialogo **ambito Management Pack Objects** selezionare l'elemento con il **candidato di individuazione** di destinazione LS e quindi fare clic su **OK**. Si noti che il candidato per l'individuazione LS verrà visualizzato solo se è stato installato il Management Pack di Lync Server 2010.

4.  Nella console di Operations Manager fare clic con il pulsante destro del mouse su **candida scoperta**, scegliere **sostituzioni**, scegliere **Sostituisci individuazione oggetti**e quindi fare clic su **per tutti gli oggetti della classe: LS Discovery candidate**.

5.  Nella finestra di dialogo **Sostituisci proprietà** selezionare la casella di controllo **Sostituisci** accanto al **nome completo di Watchernode di individuazione centrale**dei parametri. Digitare il nome di dominio completo del computer Lync Server 2010 nelle caselle **valore di override** e **valore effettivo** . Selezionare la casella di controllo **imposta** e fare clic su **OK**.

Dopo aver creato l'override, è necessario riavviare il servizio integrità nel server di gestione radice. Per riavviare il servizio integrità, completare la procedura seguente nel server di gestione radice:

1.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Accessori**, fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.

2.  Nella finestra della console digitare il comando seguente e quindi premere INVIO:
    
        Net stop HealthService

3.  Verrà visualizzato un messaggio che indica che "il servizio di gestione di System Center si arresta", seguito da un secondo messaggio che indica che il servizio è stato interrotto. Dopo l'interruzione del servizio, è possibile riavviarlo digitando il comando seguente e premendo INVIO:
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a>Verificare che il nuovo candidato di individuazione centrale sia stato individuato

Il passaggio finale prima dell'aggiornamento di Central Management store consiste nel verificare che il nuovo candidato di individuazione centrale sia stato individuato dal Management Pack di Lync Server 2010. A questo scopo, aprire la console di Operations Manager e quindi fare clic su monitoraggio. Nella scheda Monitoraggio espandere **Microsoft Lync Server 2010 Health**, espandere **individuazione topologia**e quindi fare clic su **visualizzazione stato individuazione**. Verificare che una riga nella visualizzazione contenga un **percorso** che elenchi il nome di dominio completo del candidato di individuazione centrale. Dovresti anche verificare che lo stato del computer sia segnalato come **integro**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

