---
title: Associare i rapporti di monitoraggio a un database mirror in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Riepilogo: informazioni su come associare i rapporti di monitoraggio a un database mirror utilizzato da Skype for Business Server.'
ms.openlocfilehash: 4ce6d420f6b29a5c6160b9b220e5fd190a977f9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802166"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a><span data-ttu-id="f4b9b-103">Associare i rapporti di monitoraggio a un database mirror in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f4b9b-103">Associate Monitoring Reports with a mirror database in Skype for Business Server</span></span> 
 
<span data-ttu-id="f4b9b-104">**Riepilogo:** Informazioni su come associare i rapporti di monitoraggio a un database mirror utilizzato da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f4b9b-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="f4b9b-105">Monitorare i report con un database mirror</span><span class="sxs-lookup"><span data-stu-id="f4b9b-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="f4b9b-106">Se si configura un mirror per il database di monitoraggio, tale database mirror prenderà il controllo come database primario in caso di failover.</span><span class="sxs-lookup"><span data-stu-id="f4b9b-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="f4b9b-107">Tuttavia, se si utilizzano i rapporti di monitoraggio di Skype for Business Server e si verifica un failover, è possibile che i rapporti di monitoraggio non si connettono al database mirror.</span><span class="sxs-lookup"><span data-stu-id="f4b9b-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="f4b9b-108">Questo perché, quando si installaNo i rapporti di monitoraggio, si specifica solo il percorso del database primario. non si specifica il percorso del database mirror.</span><span class="sxs-lookup"><span data-stu-id="f4b9b-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="f4b9b-109">Per fare in modo che i rapporti di monitoraggio esercitino automaticamente il failover nel database mirror, è necessario aggiungere il database mirror come "partner di failover" ai due database utilizzati dai rapporti di monitoraggio (un database per i dati del record dettagli chiamata e l'altro per i dati QoE).</span><span class="sxs-lookup"><span data-stu-id="f4b9b-109">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="f4b9b-110">Tenere presente che questo passaggio deve essere eseguito dopo aver installato i rapporti di monitoraggio. È possibile aggiungere le informazioni sul partner di failover modificando manualmente i valori della stringa di connessione utilizzati da questi due database.</span><span class="sxs-lookup"><span data-stu-id="f4b9b-110">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="f4b9b-111">A tale scopo, completare la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="f4b9b-111">To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="f4b9b-112">Utilizzare Internet Explorer per aprire la **home page SQL Server Reporting Services.**</span><span class="sxs-lookup"><span data-stu-id="f4b9b-112">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="f4b9b-113">L'URL della home page di Reporting Services include:</span><span class="sxs-lookup"><span data-stu-id="f4b9b-113">The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="f4b9b-114">Prefisso **http:.**</span><span class="sxs-lookup"><span data-stu-id="f4b9b-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="f4b9b-115">Nome di dominio completo (FQDN) del computer in cui è installato Reporting Services, ad esempio **atl-sql-001.litwareinc.com**.</span><span class="sxs-lookup"><span data-stu-id="f4b9b-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="f4b9b-116">Stringa di caratteri **/Reports_**.</span><span class="sxs-lookup"><span data-stu-id="f4b9b-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="f4b9b-117">Nome dell'istanza del database in cui sono installati i rapporti di monitoraggio( ad esempio, **archinst**).</span><span class="sxs-lookup"><span data-stu-id="f4b9b-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
     <span data-ttu-id="f4b9b-118">Se ad esempio SQL Server Reporting Services è stato installato nel computer atl-sql-001.litwareinc.com e i rapporti di monitoraggio utilizzano l'archivio dell'istanza del database, l'URL della home page sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="f4b9b-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="f4b9b-119">Dopo aver eseguito l'accesso alla home page di Reporting Services, fare clic su **ServerReports** e quindi su **Reports_Content**.</span><span class="sxs-lookup"><span data-stu-id="f4b9b-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="f4b9b-120">Verrà visualizzata la pagina **Reports_Content** per i rapporti di monitoraggio di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f4b9b-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="f4b9b-121">Nella pagina **Reports_Content** fare clic sull'origine dati **CDRDB.**</span><span class="sxs-lookup"><span data-stu-id="f4b9b-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="f4b9b-122">Nella scheda Proprietà della pagina  **CDRDB** cercare la casella di testo con l'etichetta **Stringa di connessione.**</span><span class="sxs-lookup"><span data-stu-id="f4b9b-122">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="f4b9b-123">La stringa di connessione corrente sarà simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="f4b9b-123">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="f4b9b-124">Data source=(local)\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="f4b9b-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="f4b9b-125">Modificare la stringa di connessione in modo da includere il nome del server e l'istanza di database per il database mirror.</span><span class="sxs-lookup"><span data-stu-id="f4b9b-125">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="f4b9b-126">Se ad esempio il server è denominato atl-mirror-001 e il database mirror si trova nell'istanza di archiviazione, sarà necessario aggiungerlo per specificare il database mirror utilizzando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="f4b9b-126">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="f4b9b-127">Failover Partner=atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="f4b9b-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="f4b9b-128">La stringa di connessione modificata sarà simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="f4b9b-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="f4b9b-129">Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="f4b9b-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="f4b9b-130">Dopo aver aggiornato la stringa di connessione, fare clic su **Applica.**</span><span class="sxs-lookup"><span data-stu-id="f4b9b-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="f4b9b-131">Nella pagina **CDRDB** fare clic sul **Reports_Content** seguente.</span><span class="sxs-lookup"><span data-stu-id="f4b9b-131">On the **CDRDB** page, click the **Reports_Content** link.</span></span> <span data-ttu-id="f4b9b-132">Fare clic **sull'origine dati QMSDB** e quindi modificare la stringa di connessione per il database QoE.</span><span class="sxs-lookup"><span data-stu-id="f4b9b-132">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="f4b9b-133">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f4b9b-133">For example:</span></span>
    
    <span data-ttu-id="f4b9b-134">Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="f4b9b-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="f4b9b-135">Fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="f4b9b-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f4b9b-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4b9b-136">See also</span></span>

[<span data-ttu-id="f4b9b-137">Installare i rapporti di monitoraggio in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f4b9b-137">Install Monitoring Reports in Skype for Business Server</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="f4b9b-138">Utilizzo dei rapporti di monitoraggio in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f4b9b-138">Using Monitoring Reports in Skype for Business Server</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)
