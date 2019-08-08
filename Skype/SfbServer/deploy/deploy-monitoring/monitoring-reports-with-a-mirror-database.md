---
title: Associare i report di monitoraggio a un database mirror in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Riepilogo: informazioni su come associare i report di monitoraggio a un database mirror usato da Skype for Business Server.'
ms.openlocfilehash: 522ed5f9bd6e437a83e9cb3575ca92c0bd049e44
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239887"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a><span data-ttu-id="0cdff-103">Associare i report di monitoraggio a un database mirror in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0cdff-103">Associate Monitoring Reports with a mirror database in Skype for Business Server</span></span> 
 
<span data-ttu-id="0cdff-104">**Riepilogo:** Informazioni su come associare i report di monitoraggio a un database mirror usato da Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0cdff-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="0cdff-105">Monitorare i report con un database mirror</span><span class="sxs-lookup"><span data-stu-id="0cdff-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="0cdff-106">Se si configura uno specchio per il database di monitoraggio, il database mirror subentra come database principale se si verifica un failover.</span><span class="sxs-lookup"><span data-stu-id="0cdff-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="0cdff-107">Tuttavia, se si usano i report di monitoraggio di Skype for Business Server e si verifica un failover, è possibile che i report di monitoraggio non si connettono al database mirror.</span><span class="sxs-lookup"><span data-stu-id="0cdff-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="0cdff-108">Questo perché, quando si installano i report di monitoraggio, si specifica solo la posizione del database primario; non si specifica la posizione del database mirror.</span><span class="sxs-lookup"><span data-stu-id="0cdff-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="0cdff-109">Per ottenere i report di monitoraggio per il failover automatico nel database mirror, è necessario aggiungere il database mirror come "partner di failover" ai due database usati dai report di monitoraggio (un database per i dati del record di dettagli chiamata e l'altro per la qualità di Dati dell'esperienza (QoE)).</span><span class="sxs-lookup"><span data-stu-id="0cdff-109">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="0cdff-110">Notare che questo passaggio deve essere eseguito dopo aver installato i report di monitoraggio. È possibile aggiungere le informazioni del partner di failover modificando manualmente i valori della stringa di connessione usati da questi due database.</span><span class="sxs-lookup"><span data-stu-id="0cdff-110">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="0cdff-111">Per eseguire questa operazione, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="0cdff-111">To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="0cdff-112">Usare Internet Explorer per aprire la Home page di **SQL Server Reporting Services** .</span><span class="sxs-lookup"><span data-stu-id="0cdff-112">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="0cdff-113">L'URL della Home page di Reporting Services include:</span><span class="sxs-lookup"><span data-stu-id="0cdff-113">The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="0cdff-114">Prefisso **http:**</span><span class="sxs-lookup"><span data-stu-id="0cdff-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="0cdff-115">Il nome di dominio completo (FQDN) del computer in cui sono installati i servizi di Reporting (ad esempio, **ATL-SQL-001.litwareinc.com**).</span><span class="sxs-lookup"><span data-stu-id="0cdff-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="0cdff-116">La stringa di caratteri **/reports_**.</span><span class="sxs-lookup"><span data-stu-id="0cdff-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="0cdff-117">Nome dell'istanza del database in cui sono installati i report di monitoraggio, ad esempio **ARCHINST**.</span><span class="sxs-lookup"><span data-stu-id="0cdff-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
     <span data-ttu-id="0cdff-118">Ad esempio, se SQL Server Reporting Services è stato installato nel computer atl-sql-001.litwareinc.com e i report di monitoraggio usano l'istanza del database ARCHINST, l'URL della Home page sarà simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0cdff-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="0cdff-119">Dopo avere eseguito l'accesso alla Home page di Reporting Services, fare clic su **ServerReports**e quindi su **Reports_Content**.</span><span class="sxs-lookup"><span data-stu-id="0cdff-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="0cdff-120">Questo ti porterà alla pagina **Reports_Content** per i report di monitoraggio di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0cdff-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="0cdff-121">Nella pagina **Reports_Content** fare clic sull'origine dati **CDRDB** .</span><span class="sxs-lookup"><span data-stu-id="0cdff-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="0cdff-122">Nella scheda **Proprietà** della pagina **CDRDB** cercare nella casella di testo la **stringa di connessione**con etichetta.</span><span class="sxs-lookup"><span data-stu-id="0cdff-122">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="0cdff-123">La stringa di connessione corrente avrà un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0cdff-123">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="0cdff-124">Origine dati = (locale) \archinst; catalogo iniziale = LcsCDR</span><span class="sxs-lookup"><span data-stu-id="0cdff-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="0cdff-125">Modificare la stringa di connessione per includere il nome del server e l'istanza del database per il database mirror.</span><span class="sxs-lookup"><span data-stu-id="0cdff-125">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="0cdff-126">Ad esempio, se il server è denominato ATL-mirror-001 e il database mirror si trova nell'istanza di ARCHINST, sarà necessario aggiungerlo per specificare il database mirror usando la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="0cdff-126">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="0cdff-127">Partner failover = ATL-mirror-001\Archinst</span><span class="sxs-lookup"><span data-stu-id="0cdff-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="0cdff-128">La stringa di connessione modificata avrà un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="0cdff-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="0cdff-129">Origine dati = (local) \archinst; Partner di failover = ATL-mirror-001\Archinst; catalogo iniziale = LcsCDR</span><span class="sxs-lookup"><span data-stu-id="0cdff-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="0cdff-130">Dopo aver aggiornato la stringa di connessione, fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="0cdff-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="0cdff-131">Nella pagina **CDRDB** fare clic sul collegamento **Reports_Content** .</span><span class="sxs-lookup"><span data-stu-id="0cdff-131">On the **CDRDB** page, click the **Reports_Content** link.</span></span> <span data-ttu-id="0cdff-132">Fare clic sull'origine dati **QMSDB** e quindi modificare la stringa di connessione per il database QoE.</span><span class="sxs-lookup"><span data-stu-id="0cdff-132">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="0cdff-133">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0cdff-133">For example:</span></span>
    
    <span data-ttu-id="0cdff-134">Origine dati = (local) \archinst; Partner di failover = ATL-mirror-001\Archinst; catalogo iniziale = QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="0cdff-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="0cdff-135">Fare clic su **applica**.</span><span class="sxs-lookup"><span data-stu-id="0cdff-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0cdff-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0cdff-136">See also</span></span>

[<span data-ttu-id="0cdff-137">Installare report di monitoraggio in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0cdff-137">Install Monitoring Reports in Skype for Business Server</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="0cdff-138">Uso dei report di monitoraggio in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0cdff-138">Using Monitoring Reports in Skype for Business Server</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)
