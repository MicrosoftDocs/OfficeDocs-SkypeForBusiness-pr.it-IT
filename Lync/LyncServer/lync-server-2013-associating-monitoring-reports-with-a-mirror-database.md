---
title: 'Lync Server 2013: associazione dei report di monitoraggio a un database mirror'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19ff2455d473c83855320555cdffdc2e33001d0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979859"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a>Associazione di report di monitoraggio a un database mirror in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-07_

Se si configura uno specchio per il database di monitoraggio, il database mirror subentra come database principale se si verifica un failover. Tuttavia, se si usano i report di monitoraggio di Lync Server e si verifica un failover, potrebbe risultare che i report di monitoraggio non si connettono al database mirror. Questo perché, quando si installano i report di monitoraggio, si specifica solo la posizione del database primario; non si specifica la posizione del database mirror.

Per ottenere i report di monitoraggio per il failover automatico nel database mirror, è necessario aggiungere il database mirror come "partner di failover" ai due database usati dai report di monitoraggio (un database per i dati del record di dettagli chiamata e l'altro per la qualità di Dati dell'esperienza (QoE)). Notare che questo passaggio deve essere eseguito dopo aver installato i report di monitoraggio. È possibile aggiungere le informazioni del partner di failover modificando manualmente i valori della stringa di connessione usati da questi due database. Per eseguire questa operazione, eseguire la procedura seguente:

1.  Usare Internet Explorer per aprire la Home page di **SQL Server Reporting Services** . L'URL della Home page di Reporting Services include:
    
      - Prefisso **http:**
    
      - Il nome di dominio completo (FQDN) del computer in cui sono installati i servizi di Reporting (ad esempio, **ATL-SQL-001.litwareinc.com**).
    
      - La stringa di **caratteri\_/Reports**.
    
      - Nome dell'istanza del database in cui sono installati i report di monitoraggio, ad esempio **ARCHINST**.
    
    Ad esempio, se SQL Server Reporting Services è stato installato nel computer atl-sql-001.litwareinc.com e i report di monitoraggio usano l'istanza del database ARCHINST, l'URL della Home page sarà simile al seguente:
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  Dopo avere eseguito l'accesso alla Home page di Reporting Services, fare clic su **LyncServerReports**e quindi fare clic su **report\_contenuto**. Si accede alla pagina **contenuto report\_** per i report di monitoraggio di Lync Server.

3.  Nella pagina **contenuto\_report** fare clic sull'origine dati **CDRDB** .

4.  Nella scheda **Proprietà** della pagina **CDRDB** cercare nella casella di testo la **stringa di connessione**con etichetta. La stringa di connessione corrente avrà un aspetto simile al seguente:
    
    **Origine dati = (locale)\\ARCHINST; catalogo iniziale = LcsCDR**

5.  Modificare la stringa di connessione per includere il nome del server e l'istanza del database per il database mirror. Ad esempio, se il server è denominato ATL-mirror-001 e il database mirror si trova nell'istanza di ARCHINST, sarà necessario aggiungerlo per specificare il database mirror usando la sintassi seguente:
    
    **Partner di failover = ATL-mirror-\\001 ARCHINST**
    
    La stringa di connessione modificata avrà un aspetto simile al seguente:
    
    **Origine dati = (local)\\ARCHINST; Partner di failover = ATL-mirror-\\001 ARCHINST; catalogo iniziale = LcsCDR**

6.  Dopo aver aggiornato la stringa di connessione, fare clic su **applica**.

7.  Nella pagina **CDRDB** fare clic sul collegamento **contenuto\_report** . Fare clic sull'origine dati **QMSDB** e quindi modificare la stringa di connessione per il database QoE. Ad esempio:
    
    **Origine dati = (local)\\ARCHINST; Partner di failover = ATL-mirror-\\001 ARCHINST; catalogo iniziale = QoEMetrics**

8.  Fare clic su **applica**.

<div>

## <a name="see-also"></a>Vedere anche


[Installazione di report di monitoraggio di Lync Server 2013](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[Uso di report di monitoraggio in Lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

