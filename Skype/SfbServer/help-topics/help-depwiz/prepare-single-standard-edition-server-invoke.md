---
title: Preparare un singolo server Standard Edition (Invoke)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: Nella pagina esecuzione comandi in corso, le attività di installazione di SQL Server Express e di configurazione per agire come archivio di gestione centrale possono essere visualizzate nel riquadro attività. Per impostazione predefinita, viene creata un'istanza di un database basato su SQL Server denominato RTC. Vengono inoltre create regole del firewall per consentire l'accesso in entrata e in uscita, in modo che i server e i client possano comunicare con il database e l'istanza. Al termine dell'attività, è possibile selezionare il file di registro nell'elenco a discesa. Tale file è denominato Avvio automatico computer locale. Dopo avere selezionato il file di registro, fare clic su Visualizza registro. Esaminare gli eventuali errori e avvisi presenti nel file. Quando si è pronti per continuare, fare clic su Fine. Se non è stato ancora fatto, è necessario definire la topologia con il generatore di topologie.
ms.openlocfilehash: adf980ec2576eb4e23983fcd99befb1fc6bfb6ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829746"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="fdff5-111">Preparare un singolo server Standard Edition (Invoke)</span><span class="sxs-lookup"><span data-stu-id="fdff5-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="fdff5-112">Nella pagina **esecuzione comandi** in corso, le attività di installazione di SQL Server Express e di configurazione per agire come archivio di gestione centrale possono essere visualizzate nel riquadro attività.</span><span class="sxs-lookup"><span data-stu-id="fdff5-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="fdff5-113">Per impostazione predefinita, viene creata un'istanza di un database basato su SQL Server denominato RTC.</span><span class="sxs-lookup"><span data-stu-id="fdff5-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="fdff5-114">Vengono inoltre create regole del firewall per consentire l'accesso in entrata e in uscita, in modo che i server e i client possano comunicare con il database e l'istanza.</span><span class="sxs-lookup"><span data-stu-id="fdff5-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="fdff5-115">Al termine dell'attività, è possibile selezionare il file di registro nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="fdff5-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="fdff5-116">Tale file è denominato **Avvio automatico computer locale**.</span><span class="sxs-lookup"><span data-stu-id="fdff5-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="fdff5-117">Dopo avere selezionato il file di registro, fare clic su **Visualizza registro**.</span><span class="sxs-lookup"><span data-stu-id="fdff5-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="fdff5-118">Esaminare gli eventuali errori e avvisi presenti nel file.</span><span class="sxs-lookup"><span data-stu-id="fdff5-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="fdff5-119">Quando si è pronti per continuare, fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="fdff5-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="fdff5-120">Se non è stato ancora fatto, è necessario definire la topologia con il generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="fdff5-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fdff5-121">L'installazione di SQL Server Express può richiedere del tempo per il completamento.</span><span class="sxs-lookup"><span data-stu-id="fdff5-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="fdff5-122">Durante l'installazione non sono visibili indicatori di stato sullo schermo o nel riquadro attività.</span><span class="sxs-lookup"><span data-stu-id="fdff5-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="fdff5-123">Per monitorare l'installazione, è consigliabile utilizzare Windows Task Manager e cercare i processi MSIExec e i file di installazione di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="fdff5-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="fdff5-124">In questo modo è possibile visualizzare lo stato dell'installazione e assicurarsi che proceda correttamente.</span><span class="sxs-lookup"><span data-stu-id="fdff5-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="fdff5-125">A seconda dei fattori che esulano dall'ambito di questo argomento della guida, è possibile richiedere fino a 15 minuti o più per l'installazione dell'istanza di SQL Server da completare.</span><span class="sxs-lookup"><span data-stu-id="fdff5-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

