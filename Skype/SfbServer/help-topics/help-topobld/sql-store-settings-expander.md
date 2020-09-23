---
title: Espansione delle impostazioni dell'archivio SQL
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Per modificare le proprietà di un database di SQL Server, è necessario modificare l'istanza del database di SQL Server. Non è possibile usare la finestra di dialogo Modifica proprietà per azioni come lo spostamento del database del server di archiviazione da un computer all'altro. Inoltre, non è possibile utilizzare la finestra di dialogo Modifica proprietà per modificare l'istanza di SQL Server che ospita l'archivio di gestione centrale.
ms.openlocfilehash: e3b16d8c6eab4f4918ef39b3c4f1ab4d0c6fc057
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219611"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="fc39f-105">Espansione delle impostazioni dell'archivio SQL</span><span class="sxs-lookup"><span data-stu-id="fc39f-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="fc39f-106">Per modificare le proprietà di un database di SQL Server, è necessario modificare l'istanza del database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fc39f-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="fc39f-107">Non è possibile usare la finestra di dialogo **Modifica proprietà** per azioni come lo spostamento del database del server di archiviazione da un computer all'altro.</span><span class="sxs-lookup"><span data-stu-id="fc39f-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="fc39f-108">Inoltre, non è possibile utilizzare la finestra di dialogo **modifica proprietà** per modificare l'istanza di SQL Server che ospita l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="fc39f-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="fc39f-109">Modifica delle proprietà di un database di SQL Server</span><span class="sxs-lookup"><span data-stu-id="fc39f-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="fc39f-110">Per modificare l'istanza di SQL Server utilizzata da qualsiasi database diverso dall'archivio di gestione centrale, eseguire la procedura seguente in Generatore di topologie:</span><span class="sxs-lookup"><span data-stu-id="fc39f-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="fc39f-111">Per modificare un'istanza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="fc39f-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="fc39f-112">Selezionare il database corretto nel nodo **Archivi SQL** e fare clic su **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="fc39f-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="fc39f-113">Nella finestra di dialogo **Modifica proprietà** eseguire una di queste operazioni:</span><span class="sxs-lookup"><span data-stu-id="fc39f-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="fc39f-114">Per utilizzare l'istanza predefinita di SQL Server, selezionare **istanza predefinita** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc39f-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="fc39f-115">Per utilizzare un'istanza di database denominata, selezionare **Istanza denominata**, immettere il nome dell'istanza nella casella di testo e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="fc39f-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="fc39f-116">È necessario immettere solo il nome dell'istanza (ad esempio, ArchivingInstance) e non l'intero percorso di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fc39f-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="fc39f-117">Quando si utilizza la finestra di dialogo **modifica proprietà** , il generatore di topologie non verificherà che l'istanza di database immessa sia un'istanza valida.</span><span class="sxs-lookup"><span data-stu-id="fc39f-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="fc39f-118">Ad esempio, se si è inavvertitamente typeArchivingInstanec come nome dell'istanza e quindi fare clic su **OK**, generatore di topologie accetterà l'istanza non valida.</span><span class="sxs-lookup"><span data-stu-id="fc39f-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="fc39f-119">Prima di poter pubblicare la topologia, è necessario correggere l'errore: se non è possibile trovare un'istanza di SQL Server, il generatore di topologie non creerà quell'istanza per l'utente.</span><span class="sxs-lookup"><span data-stu-id="fc39f-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

