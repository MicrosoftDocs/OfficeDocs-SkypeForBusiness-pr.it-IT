---
title: Creare un database
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: Generatore di topologie consente di installare i database in un SQL Server archivio. Quando si installano database utilizzando Generatore di topologie, l'applicazione legge le informazioni dalla topologia e quindi installa i database necessari nel computer SQL Server o nel cluster SQL Server specificato. Questo è l'unico tipo di installazione di database disponibile tramite il Generatore di topologie. Se è necessario installare un database specifico in un computer specifico o se è necessario installare un database collocato, è necessario utilizzare l'interfaccia della riga di comando Windows PowerShell e il cmdlet Install-CsDatabase.
ms.openlocfilehash: 92e0c8c0221fbd697ce59587ff4543d6cf7e119d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101832"
---
# <a name="create-database"></a><span data-ttu-id="f873f-106">Creazione database</span><span class="sxs-lookup"><span data-stu-id="f873f-106">Create Database</span></span>
 
<span data-ttu-id="f873f-107">Generatore di topologie consente di installare i database in un SQL Server archivio.</span><span class="sxs-lookup"><span data-stu-id="f873f-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="f873f-108">Quando si installano database utilizzando Generatore di topologie, l'applicazione legge le informazioni dalla topologia e quindi installa i database necessari nel computer SQL Server o nel cluster SQL Server specificato.</span><span class="sxs-lookup"><span data-stu-id="f873f-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="f873f-109">Questo è l'unico tipo di installazione di database disponibile tramite il Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="f873f-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="f873f-110">Se è necessario installare un database specifico in un computer specifico o se è necessario installare un database collocato, è necessario utilizzare invece l'interfaccia della riga di comando Windows PowerShell e il cmdlet [Install-CsDatabase.](/powershell/module/skype/install-csdatabase?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="f873f-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="f873f-111">Creazione di un database</span><span class="sxs-lookup"><span data-stu-id="f873f-111">Creating a Database</span></span>

1. <span data-ttu-id="f873f-112">Fare clic sul nodo Skype for Business Server e quindi su **Installa database.**</span><span class="sxs-lookup"><span data-stu-id="f873f-112">Click the Skype for Business Server node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="f873f-113">Nella **pagina** Crea database della  finestra di dialogo Installa database selezionare il nome di dominio completo (FQDN) dell'archivio SQL Server in cui devono essere creati i nuovi database.</span><span class="sxs-lookup"><span data-stu-id="f873f-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="f873f-p103">Fare clic su **Avanzate**. Nella finestra di dialogo **Seleziona percorso file di database** selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f873f-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="f873f-p104">**Determina automaticamente il percorso dei file di database**. Se si seleziona questa opzione, il Generatore di topologie userà un algoritmo predefinito per scegliere il percorso di archiviazione dei registri di database e dei file di dati.</span><span class="sxs-lookup"><span data-stu-id="f873f-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="f873f-118">**Utilizza i valori predefiniti dell'istanza di SQL Server**.</span><span class="sxs-lookup"><span data-stu-id="f873f-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="f873f-119">Se si seleziona questa opzione, non verrà usato l'algoritmo predefinito per scegliere i percorsi di archiviazione dei file di dati e dei log di database.</span><span class="sxs-lookup"><span data-stu-id="f873f-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="f873f-120">Tali file vengono invece archiviati nei percorsi predefiniti di SQL Server, configurati preventivamente da un amministratore di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f873f-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="f873f-121">I file di dati verranno perciò archiviati nel percorso dei file di dati predefinito di SQL Server, mentre i file di log verranno archiviati nel percorso dei file di log predefinito di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f873f-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="f873f-122">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f873f-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="f873f-123">Nella pagina **Creare database** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="f873f-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="f873f-124">Nella pagina **Creazione del database completata** fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="f873f-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
