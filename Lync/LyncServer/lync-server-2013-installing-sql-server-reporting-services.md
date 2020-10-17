---
title: 'Lync Server 2013: installazione di SQL Server Reporting Services'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9044f90146b604f0277b0a5b815c6540849d58b7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534933"
---
# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a>Installazione di SQL Server Reporting Services in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-20_

Se si intende utilizzare i rapporti di monitoraggio di Microsoft Lync Server 2013 (vedere la sezione successiva di questa documentazione per ulteriori informazioni), è necessario prima installare SQL Server Reporting Services. È possibile installare Reporting Services nello stesso momento in cui si installa Microsoft SQL Server o in qualsiasi momento dopo l'installazione di SQL Server. Se SQL Server non è ancora stato installato, seguire le istruzioni fornite in precedenza in questa documentazione. Durante l'installazione di SQL Server assicurarsi di selezionare Reporting Services nella pagina Selezione funzionalità. Verrà così installato SQL Server Reporting Services.

Se SQL Server è già stato installato, ma SQL Server Reporting Services non è stato incluso nell'installazione, è possibile aggiungere questa funzionalità attenendosi alle istruzioni appropriate per SQL Server 2008 R2 o SQL Server 2012, a seconda della versione in uso.

Per verificare che Reporting Services sia stato installato correttamente, eseguire le operazioni seguenti:

1.  Se si esegue Microsoft SQL Server 2008 R2, fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft SQL Server 2008 R2**, **Strumenti di configurazione** e quindi fare clic su **Gestione configurazione Reporting Services**.
    
    Se si esegue Microsoft SQL Server 2012, fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft SQL Server 2012**, **Strumenti di configurazione** e quindi fare clic su **Gestione configurazione Reporting Services**.

2.  Nella finestra di dialogo **Connessione configurazione Reporting Services** verificare che il nome del server sia visualizzato nella casella **Nome server** e che il nome dell'istanza di SQL Server in cui sono archiviati i dati di monitoraggio sia visualizzato nella casella **Istanza server di report**. Fare clic su **Connetti**.

In Gestione configurazione Reporting Services il riquadro di stato del server di report deve mostrare che è stato installato SQL Server Reporting Service e che i servizi di Reporting sono in esecuzione: lo stato del server di report deve essere visualizzato come **avviato** e il pulsante **Start** deve essere disattivato e non disponibile. Se Reporting Services risulta non in esecuzione, fare clic su**Avvia** per avviare il servizio.

Se accanto all'etichetta Nome database server di report non è elencato alcun database, eseguire le operazioni seguenti:

1.  In Gestione configurazione Reporting Services fare clic su **Database**.

2.  Nel riquadro Database server di report fare clic su **Modifica database**.

3.  Nella Configurazione guidata database del server di report	selezionare **Crea un nuovo database del server di report** nel riquadro Azione e quindi fare clic su **Avanti**.

4.  Nel riquadro Server di database della Configurazione guidata database del server di report verificare che le informazioni elencate nelle caselle **Nome server**, **Tipo di autenticazione** e **Nome utente** siano corrette. Fare clic su **Test connessione** per verificare che sia possibile attivare una connessione al server di database e quindi fare clic su **Avanti**.

5.  Nel riquadro Database della Configurazione guidata database del server di report accettare i valori predefiniti per **Nome database**, **Lingua** e **Modalità server di report**, quindi fare clic su **Avanti**.

6.  Nel riquadro Credenziali della Configurazione guidata database del server di report verificare che siano elencate le informazioni corrette nell'elenco a discesa **Tipo di autenticazione** e nelle caselle **Nome utente** e **Password**, quindi fare clic su **Avanti**.

7.  Nel riquadro Riepilogo della Configurazione guidata database del server di report fare clic su **Avanti**.

8.  Nel riquadro Continua e termina della Configurazione guidata database del server di report	 fare clic su **Fine**.

Per verificare che siano stati configurati gli URL di Reporting Services, fare clic su **URL servizio Web**. Verranno visualizzati uno o più URL sotto il titolo **URL servizio Web ReportServer**. Fare clic su ognuno di questi URL per verificare che sia possibile raggiungere la home page per l'installazione locale di SQL Server Reporting Services.

</div>

<span> </span>

</div>

</div>

</div>

