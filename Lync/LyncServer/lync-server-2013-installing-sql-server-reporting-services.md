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
ms.openlocfilehash: 6342743486e3a3261e297d602ceb994d421dc13c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a>Installazione di SQL Server Reporting Services in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-20_

Se si intende usare i report di monitoraggio di Microsoft Lync Server 2013 (vedere la sezione successiva di questa documentazione per altre informazioni), è necessario installare SQL Server Reporting Services. È possibile installare Reporting Services contemporaneamente all'installazione di Microsoft SQL Server o in qualsiasi momento dopo l'installazione di SQL Server. Se SQL Server non è installato, seguire le istruzioni fornite in precedenza in questa documentazione. Durante l'installazione di SQL Server, verificare che nella pagina Selezione funzionalità venga selezionato Reporting Services. Che installerà SQL Server Reporting Services.

Se SQL Server è già stato installato, ma non è stato installato SQL Server Reporting Services, è possibile aggiungerlo seguendo il set di istruzioni appropriato per SQL Server 2008 R2 o SQL Server 2012, in base alle esigenze.

Per verificare che Reporting Services sia stato installato correttamente, eseguire la procedura seguente:

1.  Se si esegue Microsoft SQL Server 2008 R2, fare clic sul **pulsante Start**, scegliere **tutti i programmi**, **Microsoft SQL Server 2008 R2**, **strumenti di configurazione**e quindi fare clic su **Gestione configurazione di Reporting Services**.
    
    Se si esegue Microsoft SQL Server 2012, fare clic sul **pulsante Start**, scegliere **tutti i programmi**, **Microsoft SQL Server 2012**, fare clic su **strumenti di configurazione**e quindi su **Gestione configurazione di Reporting Services**.

2.  Nella finestra di dialogo **connessione configurazione Reporting Services** verificare che il nome del server sia visualizzato nella casella **nome server** e che il nome dell'istanza di SQL Server in cui sono archiviati i dati di monitoraggio sia visualizzato nella casella **istanza del server di report** . Fare clic su **Connetti**.

In Gestione configurazione di Reporting Service il riquadro Stato del server di report deve indicare che SQL Server Reporting Services è stato installato e che i servizi di Reporting sono attualmente in uso: lo stato del server di report deve essere visualizzato come **avviato** e il pulsante **Start** deve essere disattivato e non disponibile. Se il servizio Reporting non è in corso, fare clic su **Start** per avviare il servizio.

Se non è elencato alcun database accanto all'etichetta del nome del database del server di report, eseguire le operazioni seguenti:

1.  In Gestione configurazione di Reporting Services fare clic su **database**.

2.  Nel riquadro database server di report fare clic su **Cambia database**.

3.  Nel riquadro azioni della configurazione guidata database server report selezionare **Crea un nuovo database del server di report** e quindi fare clic su **Avanti**.

4.  Nel riquadro Server database della configurazione guidata database server di report verificare che le informazioni elencate nelle caselle **nome server**, **tipo di autenticazione**e nome **utente** siano corrette. Fare clic su **Test connessione** per verificare che sia possibile effettuare una connessione al server di database e quindi fare clic su **Avanti**.

5.  Nel riquadro database della configurazione guidata database server report accettare i valori predefiniti per il **nome del database**, la **lingua**e la **modalità server di report** e quindi fare clic su **Avanti**.

6.  Nel riquadro credenziali della configurazione guidata database del server di report verificare che le informazioni corrette siano elencate nell'elenco a discesa **tipo di autenticazione** e nelle caselle **nome utente** e **password** e quindi fare clic su **Avanti**.

7.  Nel riquadro di riepilogo della configurazione guidata database server di report fare clic su **Avanti**.

8.  Nel riquadro Stato e fine della configurazione guidata database server di report fare clic su **fine**.

Per verificare che gli URL del servizio di Reporting siano stati configurati, fare clic su **URL servizio Web**. Nella sezione **URL del servizio Web ReportServer del server report**verrà visualizzato uno o più URL. Fare clic su ognuno di questi URL per verificare che sia possibile accedere alla Home page per l'installazione locale di SQL Server Reporting Services.

</div>

<span> </span>

</div>

</div>

</div>

