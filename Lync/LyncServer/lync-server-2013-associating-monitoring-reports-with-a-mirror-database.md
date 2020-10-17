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
# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a><span data-ttu-id="c06f9-103">Associazione dei rapporti di monitoraggio a un database mirror in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c06f9-103">Associating Monitoring Reports with a mirror database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c06f9-104">_**Ultimo argomento modificato:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="c06f9-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="c06f9-105">Se si configura un mirror per il database di monitoraggio, il database mirror avrà il sopravvento come database primario se si verifica un failover.</span><span class="sxs-lookup"><span data-stu-id="c06f9-105">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="c06f9-106">Tuttavia, se si utilizzano i rapporti di monitoraggio di Lync Server e si verifica un failover, potrebbe risultare che i rapporti di monitoraggio non si connettono al database mirror.</span><span class="sxs-lookup"><span data-stu-id="c06f9-106">However, if you use Lync Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="c06f9-107">Ciò è dovuto al fatto che, quando si installano i rapporti di monitoraggio, si specifica solo il percorso del database primario. non è possibile specificare il percorso del database mirror.</span><span class="sxs-lookup"><span data-stu-id="c06f9-107">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>

<span data-ttu-id="c06f9-108">Per ottenere il failover automatico dei rapporti di monitoraggio per il database mirror, è necessario aggiungere il database mirror come "partner di failover" ai due database utilizzati dai report di monitoraggio (un database per i dati dei record dettagli chiamata e l'altro per i dati QoE).</span><span class="sxs-lookup"><span data-stu-id="c06f9-108">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="c06f9-109">Tenere presente che questo passaggio deve essere eseguito dopo aver installato i report di monitoraggio. È possibile aggiungere le informazioni del partner di failover modificando manualmente i valori della stringa di connessione utilizzati dai due database.</span><span class="sxs-lookup"><span data-stu-id="c06f9-109">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="c06f9-110">A tale scopo, completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="c06f9-110">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="c06f9-111">Utilizzare Internet Explorer per aprire la Home page di **SQL Server Reporting Services** .</span><span class="sxs-lookup"><span data-stu-id="c06f9-111">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="c06f9-112">L'URL della Home page di Reporting Services include:</span><span class="sxs-lookup"><span data-stu-id="c06f9-112">The Reporting Services home page URL includes:</span></span>
    
      - <span data-ttu-id="c06f9-113">Il prefisso **http:** .</span><span class="sxs-lookup"><span data-stu-id="c06f9-113">The **http:** prefix.</span></span>
    
      - <span data-ttu-id="c06f9-114">Il nome di dominio completo (FQDN) del computer in cui sono installati i servizi di Reporting (ad esempio, **ATL-SQL-001.litwareinc.com**).</span><span class="sxs-lookup"><span data-stu-id="c06f9-114">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
      - <span data-ttu-id="c06f9-115">La stringa di **caratteri \_ /Reports**.</span><span class="sxs-lookup"><span data-stu-id="c06f9-115">The character string **/Reports\_**.</span></span>
    
      - <span data-ttu-id="c06f9-116">Nome dell'istanza del database in cui sono installati i rapporti di monitoraggio (ad esempio, **ARCHINST**).</span><span class="sxs-lookup"><span data-stu-id="c06f9-116">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="c06f9-117">Ad esempio, se SQL Server Reporting Services è stato installato nel computer atl-sql-001.litwareinc.com e i rapporti di monitoraggio utilizzano l'istanza del database ARCHINST, l'URL della Home Page avrà l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="c06f9-117">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  <span data-ttu-id="c06f9-118">Dopo aver eseguito l'accesso alla Home page di Reporting Services, fare clic su **LyncServerReports**, quindi fare clic su **report \_ contenuto**.</span><span class="sxs-lookup"><span data-stu-id="c06f9-118">After you have accessed the Reporting Services home page, click **LyncServerReports**, and then click **Reports\_Content**.</span></span> <span data-ttu-id="c06f9-119">Che conterrà la pagina di \*\* \_ contenuto dei report\*\* per i report di monitoraggio di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c06f9-119">That will take you to the **Reports\_Content** page for the Lync Server Monitoring Reports.</span></span>

3.  <span data-ttu-id="c06f9-120">Nella pagina \*\* \_ contenuto report\*\* fare clic sull'origine dati **CDRDB** .</span><span class="sxs-lookup"><span data-stu-id="c06f9-120">On the **Reports\_Content** page, click the **CDRDB** data source.</span></span>

4.  <span data-ttu-id="c06f9-121">Nella scheda **Proprietà** della pagina **CDRDB** cercare la casella di testo denominata **stringa di connessione**.</span><span class="sxs-lookup"><span data-stu-id="c06f9-121">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="c06f9-122">La stringa di connessione corrente avrà un aspetto analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="c06f9-122">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="c06f9-123">**Data Source = (local) \\ ARCHINST; Initial Catalog = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="c06f9-123">**Data source=(local)\\archinst;initial catalog=LcsCDR**</span></span>

5.  <span data-ttu-id="c06f9-124">Modificare la stringa di connessione per includere il nome del server e l'istanza del database per il database mirror.</span><span class="sxs-lookup"><span data-stu-id="c06f9-124">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="c06f9-125">Ad esempio, se il server è denominato ATL-mirror-001 e il database mirror si trova nell'istanza di ARCHINST, sarà necessario aggiungere per specificare il database mirror utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="c06f9-125">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="c06f9-126">**Partner di failover = ATL-mirror-001 \\ ARCHINST**</span><span class="sxs-lookup"><span data-stu-id="c06f9-126">**Failover Partner=atl-mirror-001\\archinst**</span></span>
    
    <span data-ttu-id="c06f9-127">La stringa di connessione modificata avrà l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="c06f9-127">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="c06f9-128">**Data Source = (local) \\ ARCHINST; Partner di failover = ATL-mirror-001 \\ ARCHINST; Initial Catalog = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="c06f9-128">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**</span></span>

6.  <span data-ttu-id="c06f9-129">Dopo aver aggiornato la stringa di connessione, fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="c06f9-129">After updating the connection string, click **Apply**.</span></span>

7.  <span data-ttu-id="c06f9-130">Nella pagina **CDRDB** fare clic sul collegamento \*\* \_ contenuto rapporti\*\* .</span><span class="sxs-lookup"><span data-stu-id="c06f9-130">On the **CDRDB** page, click the **Reports\_Content** link.</span></span> <span data-ttu-id="c06f9-131">Fare clic sull'origine dati di **QMSDB** e quindi modificare la stringa di connessione per il database QoE.</span><span class="sxs-lookup"><span data-stu-id="c06f9-131">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="c06f9-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c06f9-132">For example:</span></span>
    
    <span data-ttu-id="c06f9-133">**Data Source = (local) \\ ARCHINST; Partner di failover = ATL-mirror-001 \\ ARCHINST; Initial Catalog = QoEMetrics**</span><span class="sxs-lookup"><span data-stu-id="c06f9-133">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**</span></span>

8.  <span data-ttu-id="c06f9-134">Fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="c06f9-134">Click **Apply**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="c06f9-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c06f9-135">See Also</span></span>


[<span data-ttu-id="c06f9-136">Installazione dei rapporti di monitoraggio di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c06f9-136">Installing Lync Server 2013 Monitoring Reports</span></span>](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[<span data-ttu-id="c06f9-137">Utilizzo di report di monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c06f9-137">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

