---
title: Expander delle impostazioni di SQL Store
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: Per modificare le proprietà di un database di SQL Server, è necessario modificare l'istanza di database di SQL Server. Non è possibile usare la finestra di dialogo Modifica proprietà per eseguire attività come lo spostamento del database del server di archiviazione da un computer a un altro. Inoltre, non è possibile usare la finestra di dialogo Modifica proprietà per modificare l'istanza di SQL Server che ospita l'Central Management store.
ms.openlocfilehash: 816733627bcaf1156e5ad34955bb8aa9cf580642
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195430"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="50f66-105">Expander delle impostazioni di SQL Store</span><span class="sxs-lookup"><span data-stu-id="50f66-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="50f66-106">Per modificare le proprietà di un database di SQL Server, è necessario modificare l'istanza di database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="50f66-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="50f66-107">Non è possibile usare la finestra di dialogo **modifica proprietà** per eseguire attività come lo spostamento del database del server di archiviazione da un computer a un altro.</span><span class="sxs-lookup"><span data-stu-id="50f66-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="50f66-108">Inoltre, non è possibile usare la finestra di dialogo **modifica proprietà** per modificare l'istanza di SQL Server che ospita l'Central Management store.</span><span class="sxs-lookup"><span data-stu-id="50f66-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="50f66-109">Modifica delle proprietà di un database di SQL Server</span><span class="sxs-lookup"><span data-stu-id="50f66-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="50f66-110">Per modificare l'istanza di SQL Server utilizzata da qualsiasi database diverso da Central Management store, completare la procedura seguente in Generatore di topologie:</span><span class="sxs-lookup"><span data-stu-id="50f66-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="50f66-111">Per modificare un'istanza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="50f66-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="50f66-112">Selezionare il database appropriato nel nodo **Archivi SQL** e quindi fare clic su **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="50f66-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="50f66-113">Nella finestra di dialogo **modifica proprietà** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="50f66-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="50f66-114">Per usare l'istanza predefinita di SQL Server, selezionare **istanza predefinita** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="50f66-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="50f66-115">Per usare un'istanza di database denominata, selezionare **istanza denominata**, immettere il nome dell'istanza nella casella di testo e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="50f66-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="50f66-116">È necessario immettere solo il nome dell'istanza, ad esempio ArchivingInstance, e non l'intero percorso di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="50f66-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="50f66-117">Quando si lavora nella finestra di dialogo **modifica proprietà** , generatore di topologia non verificherà che l'istanza di database immessa sia un'istanza valida.</span><span class="sxs-lookup"><span data-stu-id="50f66-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="50f66-118">Ad esempio, se typeArchivingInstanec inavvertitamente come nome dell'istanza e quindi fai clic su **OK**, generatore di topologie accetterà l'istanza non valida.</span><span class="sxs-lookup"><span data-stu-id="50f66-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="50f66-119">Prima di poter pubblicare la topologia, è necessario correggere l'errore: se non è possibile trovare un'istanza di SQL Server, il generatore di topologia non creerà l'istanza desiderata.</span><span class="sxs-lookup"><span data-stu-id="50f66-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

