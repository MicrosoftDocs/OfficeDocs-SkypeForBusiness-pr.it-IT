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

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a><span data-ttu-id="49b41-102">Associazione di report di monitoraggio a un database mirror in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49b41-102">Associating Monitoring Reports with a mirror database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49b41-103">_**Argomento Ultima modifica:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="49b41-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="49b41-104">Se si configura uno specchio per il database di monitoraggio, il database mirror subentra come database principale se si verifica un failover.</span><span class="sxs-lookup"><span data-stu-id="49b41-104">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="49b41-105">Tuttavia, se si usano i report di monitoraggio di Lync Server e si verifica un failover, potrebbe risultare che i report di monitoraggio non si connettono al database mirror.</span><span class="sxs-lookup"><span data-stu-id="49b41-105">However, if you use Lync Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="49b41-106">Questo perché, quando si installano i report di monitoraggio, si specifica solo la posizione del database primario; non si specifica la posizione del database mirror.</span><span class="sxs-lookup"><span data-stu-id="49b41-106">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>

<span data-ttu-id="49b41-107">Per ottenere i report di monitoraggio per il failover automatico nel database mirror, è necessario aggiungere il database mirror come "partner di failover" ai due database usati dai report di monitoraggio (un database per i dati del record di dettagli chiamata e l'altro per la qualità di Dati dell'esperienza (QoE)).</span><span class="sxs-lookup"><span data-stu-id="49b41-107">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="49b41-108">Notare che questo passaggio deve essere eseguito dopo aver installato i report di monitoraggio. È possibile aggiungere le informazioni del partner di failover modificando manualmente i valori della stringa di connessione usati da questi due database.</span><span class="sxs-lookup"><span data-stu-id="49b41-108">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="49b41-109">Per eseguire questa operazione, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="49b41-109">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="49b41-110">Usare Internet Explorer per aprire la Home page di **SQL Server Reporting Services** .</span><span class="sxs-lookup"><span data-stu-id="49b41-110">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="49b41-111">L'URL della Home page di Reporting Services include:</span><span class="sxs-lookup"><span data-stu-id="49b41-111">The Reporting Services home page URL includes:</span></span>
    
      - <span data-ttu-id="49b41-112">Prefisso **http:**</span><span class="sxs-lookup"><span data-stu-id="49b41-112">The **http:** prefix.</span></span>
    
      - <span data-ttu-id="49b41-113">Il nome di dominio completo (FQDN) del computer in cui sono installati i servizi di Reporting (ad esempio, **ATL-SQL-001.litwareinc.com**).</span><span class="sxs-lookup"><span data-stu-id="49b41-113">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
      - <span data-ttu-id="49b41-114">La stringa di **caratteri\_/Reports**.</span><span class="sxs-lookup"><span data-stu-id="49b41-114">The character string **/Reports\_**.</span></span>
    
      - <span data-ttu-id="49b41-115">Nome dell'istanza del database in cui sono installati i report di monitoraggio, ad esempio **ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="49b41-115">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="49b41-116">Ad esempio, se SQL Server Reporting Services è stato installato nel computer atl-sql-001.litwareinc.com e i report di monitoraggio usano l'istanza del database ARCHINST, l'URL della Home page sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="49b41-116">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  <span data-ttu-id="49b41-117">Dopo avere eseguito l'accesso alla Home page di Reporting Services, fare clic su **LyncServerReports**e quindi fare clic su **report\_contenuto**.</span><span class="sxs-lookup"><span data-stu-id="49b41-117">After you have accessed the Reporting Services home page, click **LyncServerReports**, and then click **Reports\_Content**.</span></span> <span data-ttu-id="49b41-118">Si accede alla pagina **contenuto report\_** per i report di monitoraggio di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="49b41-118">That will take you to the **Reports\_Content** page for the Lync Server Monitoring Reports.</span></span>

3.  <span data-ttu-id="49b41-119">Nella pagina **contenuto\_report** fare clic sull'origine dati **CDRDB** .</span><span class="sxs-lookup"><span data-stu-id="49b41-119">On the **Reports\_Content** page, click the **CDRDB** data source.</span></span>

4.  <span data-ttu-id="49b41-120">Nella scheda **Proprietà** della pagina **CDRDB** cercare nella casella di testo la **stringa di connessione**con etichetta.</span><span class="sxs-lookup"><span data-stu-id="49b41-120">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="49b41-121">La stringa di connessione corrente avrà un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="49b41-121">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="49b41-122">**Origine dati = (locale)\\ARCHINST; catalogo iniziale = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="49b41-122">**Data source=(local)\\archinst;initial catalog=LcsCDR**</span></span>

5.  <span data-ttu-id="49b41-123">Modificare la stringa di connessione per includere il nome del server e l'istanza del database per il database mirror.</span><span class="sxs-lookup"><span data-stu-id="49b41-123">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="49b41-124">Ad esempio, se il server è denominato ATL-mirror-001 e il database mirror si trova nell'istanza di ARCHINST, sarà necessario aggiungerlo per specificare il database mirror usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="49b41-124">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="49b41-125">**Partner di failover = ATL-mirror-\\001 ARCHINST**</span><span class="sxs-lookup"><span data-stu-id="49b41-125">**Failover Partner=atl-mirror-001\\archinst**</span></span>
    
    <span data-ttu-id="49b41-126">La stringa di connessione modificata avrà un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="49b41-126">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="49b41-127">**Origine dati = (local)\\ARCHINST; Partner di failover = ATL-mirror-\\001 ARCHINST; catalogo iniziale = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="49b41-127">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**</span></span>

6.  <span data-ttu-id="49b41-128">Dopo aver aggiornato la stringa di connessione, fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="49b41-128">After updating the connection string, click **Apply**.</span></span>

7.  <span data-ttu-id="49b41-129">Nella pagina **CDRDB** fare clic sul collegamento **contenuto\_report** .</span><span class="sxs-lookup"><span data-stu-id="49b41-129">On the **CDRDB** page, click the **Reports\_Content** link.</span></span> <span data-ttu-id="49b41-130">Fare clic sull'origine dati **QMSDB** e quindi modificare la stringa di connessione per il database QoE.</span><span class="sxs-lookup"><span data-stu-id="49b41-130">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="49b41-131">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="49b41-131">For example:</span></span>
    
    <span data-ttu-id="49b41-132">**Origine dati = (local)\\ARCHINST; Partner di failover = ATL-mirror-\\001 ARCHINST; catalogo iniziale = QoEMetrics**</span><span class="sxs-lookup"><span data-stu-id="49b41-132">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**</span></span>

8.  <span data-ttu-id="49b41-133">Fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="49b41-133">Click **Apply**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="49b41-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49b41-134">See Also</span></span>


[<span data-ttu-id="49b41-135">Installazione di report di monitoraggio di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49b41-135">Installing Lync Server 2013 Monitoring Reports</span></span>](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[<span data-ttu-id="49b41-136">Uso di report di monitoraggio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49b41-136">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

