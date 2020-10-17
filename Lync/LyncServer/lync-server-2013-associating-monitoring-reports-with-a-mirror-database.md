---
title: 'Lync Server 2013: associazione dei rapporti di monitoraggio a un database mirror'
description: 'Lync Server 2013: associazione dei rapporti di monitoraggio a un database mirror.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d64b37901e7939b5e904dec73caac2d3483e2d71
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568802"
---
# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a>Associazione dei rapporti di monitoraggio a un database mirror in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-07_

Se si configura un mirror per il database di monitoraggio, il database mirror avrà il sopravvento come database primario se si verifica un failover. Tuttavia, se si utilizzano i rapporti di monitoraggio di Lync Server e si verifica un failover, potrebbe risultare che i rapporti di monitoraggio non si connettono al database mirror. Ciò è dovuto al fatto che, quando si installano i rapporti di monitoraggio, si specifica solo il percorso del database primario. non è possibile specificare il percorso del database mirror.

Per ottenere il failover automatico dei rapporti di monitoraggio per il database mirror, è necessario aggiungere il database mirror come "partner di failover" ai due database utilizzati dai report di monitoraggio (un database per i dati dei record dettagli chiamata e l'altro per i dati QoE). Tenere presente che questo passaggio deve essere eseguito dopo aver installato i report di monitoraggio. È possibile aggiungere le informazioni del partner di failover modificando manualmente i valori della stringa di connessione utilizzati dai due database. A tale scopo, completare la procedura seguente:

1.  Utilizzare Internet Explorer per aprire la Home page di **SQL Server Reporting Services** . L'URL della Home page di Reporting Services include:
    
      - Il prefisso **http:** .
    
      - Il nome di dominio completo (FQDN) del computer in cui sono installati i servizi di Reporting (ad esempio, **ATL-SQL-001.litwareinc.com**).
    
      - La stringa di **caratteri \_ /Reports**.
    
      - Nome dell'istanza del database in cui sono installati i rapporti di monitoraggio (ad esempio, **ARCHINST**).
    
    Ad esempio, se SQL Server Reporting Services è stato installato nel computer atl-sql-001.litwareinc.com e i rapporti di monitoraggio utilizzano l'istanza del database ARCHINST, l'URL della Home Page avrà l'aspetto seguente:
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  Dopo aver eseguito l'accesso alla Home page di Reporting Services, fare clic su **LyncServerReports**, quindi fare clic su **report \_ contenuto**. Che conterrà la pagina di ** \_ contenuto dei report** per i report di monitoraggio di Lync Server.

3.  Nella pagina ** \_ contenuto report** fare clic sull'origine dati **CDRDB** .

4.  Nella scheda **Proprietà** della pagina **CDRDB** cercare la casella di testo denominata **stringa di connessione**. La stringa di connessione corrente avrà un aspetto analogo al seguente:
    
    **Data Source = (local) \\ ARCHINST; Initial Catalog = LcsCDR**

5.  Modificare la stringa di connessione per includere il nome del server e l'istanza del database per il database mirror. Ad esempio, se il server è denominato ATL-mirror-001 e il database mirror si trova nell'istanza di ARCHINST, sarà necessario aggiungere per specificare il database mirror utilizzando la sintassi seguente:
    
    **Partner di failover = ATL-mirror-001 \\ ARCHINST**
    
    La stringa di connessione modificata avrà l'aspetto seguente:
    
    **Data Source = (local) \\ ARCHINST; Partner di failover = ATL-mirror-001 \\ ARCHINST; Initial Catalog = LcsCDR**

6.  Dopo aver aggiornato la stringa di connessione, fare clic su **applica**.

7.  Nella pagina **CDRDB** fare clic sul collegamento ** \_ contenuto rapporti** . Fare clic sull'origine dati di **QMSDB** e quindi modificare la stringa di connessione per il database QoE. Ad esempio:
    
    **Data Source = (local) \\ ARCHINST; Partner di failover = ATL-mirror-001 \\ ARCHINST; Initial Catalog = QoEMetrics**

8.  Fare clic su **Applica**.

<div>

## <a name="see-also"></a>Vedere anche


[Installazione dei rapporti di monitoraggio di Lync Server 2013](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[Utilizzo di report di monitoraggio in Lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

