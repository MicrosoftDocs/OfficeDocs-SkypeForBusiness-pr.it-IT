---
title: Utilizzo dei Management Pack di Lync Server 2010 in uno scenario di coesistenza
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
ms.openlocfilehash: bb614726458f2cf9c77bdfe740ddb13d99d54f2f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529923"
---
# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a>Utilizzo dei Management Pack di Lync Server 2010 in uno scenario di coesistenza

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

Molti clienti adottano un programma di implementazione all'interno delle proprie aziende in cui gli utenti vengono progressivamente migrati da Microsoft Lync Server 2010 a Lync Server 2013. Gli amministratori di queste società si preoccuperanno del monitoraggio di entrambe le versioni di Lync Server per garantire che tutti gli utenti finali possano ottenere la migliore esperienza di comunicazione possibile. Per questo scenario, il Management Pack di Lync Server 2013 supporta un percorso di migrazione affiancato con Lync Server 2010 Management Pack.

In Lync Server 2010, i computer Lync Server sono stati individuati tramite il documento della topologia archiviato con l'archivio di gestione centrale. In questa configurazione, un singolo computer segnala l'esistenza di tutti gli altri computer Lync Server.

I Management Pack per Lync Server 2013 ora utilizzano l'individuazione a livello di computer invece del meccanismo di individuazione centrale utilizzato in Lync Server 2010. Ciò significa che ogni agente System Center individua se stesso e segnala la sua esistenza a System Center Operations Manager. L'utilizzo dell'individuazione a livello di computer semplifica l'amministrazione dell'infrastruttura di System Center e consente anche diverse versioni dei Management Pack di Lync Server (ad esempio, i Management Pack per Lync Server 2010 e i Management Pack per Lync Server 2013) per coesistere più facilmente.

Per supportare la migrazione, è necessario prima di tutto aggiornare il monitoraggio di Lync Server 2010 esistente per evitare lacune nella copertura. A tale scopo, eleggere un computer Lync Server 2010 esistente per il servizio dello script di individuazione centrale per Lync Server 2010 prima di eseguire l'aggiornamento dell'archivio di gestione centrale a Lync Server 2013. Questo processo si articola in quattro passaggi:

1.  Eseguire l'aggiornamento dei Management Pack di Lync Server 2010 all'aggiornamento cumulativo 7.

2.  Indicare a un computer Lync Server 2010 di eseguire lo script di individuazione centrale.

3.  Eseguire l'override del candidato di individuazione centrale in Microsoft Lync Server 2010 Management Pack.

4.  Verificare che il nuovo candidato di individuazione centrale sia stato individuato.

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a>Impostazione di un computer Lync Server 2010 per l'esecuzione dello script di individuazione centrale

Per nominare un computer dell'archivio di gestione non centrale, ad esempio un server Lync Server front end, per gestire l'individuazione centrale, è necessario creare la seguente chiave del registro di sistema nel server di gestione non centrale:

HKLM \\ software \\ Microsoft \\ Real-Time Communications \\ Health \\ CentralDiscoveryCandidate

È possibile creare questa chiave del Registro di sistema completando la procedura seguente:

1.  Fare clic sul pulsante **Start**, quindi scegliere **Esegui**.

2.  Nella finestra di dialogo **Esegui** digitare **regedit** e quindi premere INVIO.

3.  In Editor del registro di sistema espandere **HKEY \_ \_ computer locale**, espandere **software**, espandere **Microsoft**e quindi espandere **comunicazioni in tempo reale**.

4.  Fare clic con il pulsante destro del mouse su **Health**, scegliere **Nuovo** e quindi **Chiave**. Se la chiave **Health** non esiste, fare clic con il pulsante destro del mouse su **Real-Time Communications**, scegliere **Nuovo** e quindi **Chiave**. Dopo aver creato la nuova chiave, digitare Health e premere INVIO.
    
    Dopo aver creato la nuova chiave, digitare **CentralDiscoveryCandidate** e quindi premere INVIO per rinominarla.

L'acquisizione di questa modifica da parte del computer può richiedere diverse ore. Per fare in modo che la modifica venga applicata immediatamente, arrestare e quindi riavviare il servizio Agente integrità. Per riavviare il servizio agente di integrità, eseguire la procedura seguente nel computer Lync Server 2010:

1.  Fare clic su **Start**, scegliere **Tutti i programmi** e **Accessori**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e quindi scegliere **Esegui come amministratore**.

2.  Nella finestra della console digitare il comando seguente e premere INVIO:
    
        Net stop HealthService

3.  Verrà visualizzato un messaggio indicante che il servizio System Center Management è in fase di arresto, seguito da un secondo messaggio di conferma dell'avvenuto arresto. Dopo che il servizio è stato arrestato, è possibile riavviarlo digitando il comando seguente e premendo INVIO:
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a>Sostituzione del candidato di individuazione centrale in Lync Server 2010 Management Pack

Dopo aver insegnato a un computer Lync Server 2010 a segnalare i computer Lync Server 2010, è necessario informare anche il Management Pack di Lync Server 2010 su questa modifica. A tale scopo, sarà necessario creare una sostituzione in Management Pack. A tale scopo, effettuare la procedura seguente:

1.  Nella console di Operations Manager fare clic su **Creazione e modifica**.

2.  Nella scheda Creazione e modifica espandere **Oggetti Management Pack**, fare clic su **Individuazioni oggetti** e quindi fare clic su **Ambito**.

3.  Nella finestra di dialogo **Crea ambito oggetti Management Pack in base a destinazioni** selezionare l'elemento con destinazione il **candidato di individuazione LS** e fare clic su **OK**. Si noti che il candidato di individuazione LS verrà visualizzato solo se è stato installato il Management Pack di Lync Server 2010.

4.  Nella console di Operations Manager fare clic con il pulsante destro del mouse sul **candidato individuazione LS**, scegliere **Sostituzione**, **Sostituzione individuazione oggetto** e fare clic su **Per tutti gli oggetti della classe: candidato individuazione LS**.

5.  Nella finestra di dialogo **Proprietà di sostituzione** selezionare la casella di controllo **Sostituzione** accanto al parametro **FQDN WatcherNode individuazione centrale**. Digitare il nome di dominio completo del computer Lync Server 2010 nelle caselle **valore di sostituzione** e **valore effettivo** . Selezionare la casella di controllo **Imposto** e fare clic su **OK**.

Dopo aver creato la sostituzione, è necessario riavviare il servizio di integrità nel server di gestione radice. Per riavviare il servizio di integrità, completare la procedura seguente nel server di gestione radice:

1.  Fare clic su **Start**, scegliere **Tutti i programmi** e **Accessori**, fare clic con il pulsante destro del mouse su **Prompt dei comandi** e quindi scegliere **Esegui come amministratore**.

2.  Nella finestra della console digitare il comando seguente e premere INVIO:
    
        Net stop HealthService

3.  Verrà visualizzato un messaggio indicante che il servizio System Center Management è in fase di arresto, seguito da un secondo messaggio di conferma dell'avvenuto arresto. Dopo che il servizio è stato arrestato, è possibile riavviarlo digitando il comando seguente e premendo INVIO:
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a>Verifica dell'individuazione del nuovo candidato di individuazione centrale

Il passaggio finale prima dell'aggiornamento dell'archivio di gestione centrale consiste nel verificare che il nuovo candidato di individuazione centrale sia stato individuato dal Management Pack di Lync Server 2010. A tale scopo, aprire la console di Operations Manager  e quindi fare clic su Monitoraggio. Nella scheda Monitoraggio espandere **Integrità Microsoft Lync Server 2010**, **Individuazione topologia** e quindi la **vista dello stato di individuazione**. Verificare che una riga nella vista presenti un **percorso** indicante il nome di dominio completo del candidato di individuazione centrale. È inoltre necessario verificare che lo stato del computer risulti **integro**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

