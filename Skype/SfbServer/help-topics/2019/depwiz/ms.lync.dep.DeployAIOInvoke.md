---
title: Preparare un singolo server Standard Edition (Invoke)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: Nella pagina esecuzione dei comandi, le attività di installazione di SQL Server Express e configurazione per fungere da Central Management Store possono essere visualizzate nel riquadro attività. Per impostazione predefinita, viene creata un'istanza di un database basato su SQL Server denominato RTC. Vengono create anche regole firewall per consentire l'accesso in ingresso e in uscita per i server e i client per comunicare con il database e l'istanza. Dopo aver completato l'attività, è possibile selezionare il file di log nell'elenco a discesa. Il file di log è denominato computer locale di bootstrap. Dopo aver selezionato il file di log, fare clic su Visualizza log. Esaminare il file di log per eventuali errori e avvisi. Quando si è pronti a procedere, fare clic su fine. Ora devi definire la topologia con generatore di topologia se non l'hai già fatto.
ms.openlocfilehash: 0a1b8245df8e50ba4da73c98e9dcb865446a0ecc
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796967"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="3d89a-111">Preparare un singolo server Standard Edition (Invoke)</span><span class="sxs-lookup"><span data-stu-id="3d89a-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="3d89a-112">Nella pagina **esecuzione dei comandi** , le attività di installazione di SQL Server Express e configurazione per fungere da Central Management Store possono essere visualizzate nel riquadro attività.</span><span class="sxs-lookup"><span data-stu-id="3d89a-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="3d89a-113">Per impostazione predefinita, viene creata un'istanza di un database basato su SQL Server denominato RTC.</span><span class="sxs-lookup"><span data-stu-id="3d89a-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="3d89a-114">Vengono create anche regole firewall per consentire l'accesso in ingresso e in uscita per i server e i client per comunicare con il database e l'istanza.</span><span class="sxs-lookup"><span data-stu-id="3d89a-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="3d89a-115">Dopo aver completato l'attività, è possibile selezionare il file di log nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="3d89a-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="3d89a-116">Il file di log è denominato **computer locale di bootstrap**.</span><span class="sxs-lookup"><span data-stu-id="3d89a-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="3d89a-117">Dopo aver selezionato il file di log, fare clic su **Visualizza log**.</span><span class="sxs-lookup"><span data-stu-id="3d89a-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="3d89a-118">Esaminare il file di log per eventuali errori e avvisi.</span><span class="sxs-lookup"><span data-stu-id="3d89a-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="3d89a-119">Quando si è pronti a procedere, fare clic su **fine.**</span><span class="sxs-lookup"><span data-stu-id="3d89a-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="3d89a-120">Ora devi definire la topologia con generatore di topologia se non l'hai già fatto.</span><span class="sxs-lookup"><span data-stu-id="3d89a-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3d89a-121">L'installazione di SQL Server Express può richiedere del tempo per il completamento.</span><span class="sxs-lookup"><span data-stu-id="3d89a-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="3d89a-122">Durante l'installazione non è visibile alcuno stato sullo schermo o nel riquadro attività.</span><span class="sxs-lookup"><span data-stu-id="3d89a-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="3d89a-123">Per monitorare l'installazione, è consigliabile usare Gestione attività di Windows e cercare i processi MSIExec e i file di configurazione per SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3d89a-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="3d89a-124">In questo modo, puoi visualizzare lo stato dell'installazione e verificare che l'installazione proceda.</span><span class="sxs-lookup"><span data-stu-id="3d89a-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="3d89a-125">A seconda dei fattori che esulano dall'ambito di questo argomento della guida, possono essere necessarie fino a 15 minuti o più per completare l'installazione dell'istanza di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="3d89a-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

