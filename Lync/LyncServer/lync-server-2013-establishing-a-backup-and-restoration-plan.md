---
title: 'Lync Server 2013: creazione di un piano di backup e ripristino'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64d9842ccb9d83fb7ce81c326008e36722e45764
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514223"
---
# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a><span data-ttu-id="25708-102">Creazione di un piano di backup e ripristino per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25708-102">Establishing a backup and restoration plan for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25708-103">_**Ultimo argomento modificato:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="25708-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="25708-104">La creazione di un piano di backup e ripristino prevede i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="25708-104">Creating a backup and restoration plan involves the following steps:</span></span>

  - <span data-ttu-id="25708-105">Sviluppo del piano.</span><span class="sxs-lookup"><span data-stu-id="25708-105">Developing the plan.</span></span>

  - <span data-ttu-id="25708-106">Implementazione del piano.</span><span class="sxs-lookup"><span data-stu-id="25708-106">Implementing the plan.</span></span>

  - <span data-ttu-id="25708-107">Gestione del piano.</span><span class="sxs-lookup"><span data-stu-id="25708-107">Maintaining the plan.</span></span>

<div>

## <a name="developing-a-backup-and-restoration-plan"></a><span data-ttu-id="25708-108">Sviluppo di un piano di backup e ripristino</span><span class="sxs-lookup"><span data-stu-id="25708-108">Developing a Backup and Restoration Plan</span></span>

<span data-ttu-id="25708-109">Dopo aver sviluppato la strategia di backup e ripristino per Lync Server, utilizzarla per documentare un piano di backup e ripristino dettagliato.</span><span class="sxs-lookup"><span data-stu-id="25708-109">After you develop your backup and restoration strategy for Lync Server, use it to document a detailed backup and restoration plan.</span></span> <span data-ttu-id="25708-110">Il piano deve comunicare chiaramente le priorità e i requisiti per il backup di dati e impostazioni.</span><span class="sxs-lookup"><span data-stu-id="25708-110">Your plan should clearly convey the priorities and requirements for backing up data and settings.</span></span> <span data-ttu-id="25708-111">È possibile utilizzare le informazioni contenute nella [creazione di una strategia di backup e ripristino per Lync server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) e fogli di lavoro in fogli di lavoro di [backup e ripristino per Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) per facilitare la documentazione della propria strategia.</span><span class="sxs-lookup"><span data-stu-id="25708-111">You can use the information in [Establishing a backup and restoration strategy for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) and the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) to facilitate the documentation of your strategy.</span></span> <span data-ttu-id="25708-112">Il piano deve inoltre contenere criteri in base ai quali stabilire quando e come ripristinare il servizio.</span><span class="sxs-lookup"><span data-stu-id="25708-112">Your plan should also contain criteria for deciding when and how to restore service.</span></span>

<span data-ttu-id="25708-113">Quando si sviluppa il piano, è necessario prendere in considerazione e tenere conto di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="25708-113">As you develop your plan, you need to consider, and account for, the following:</span></span>

  - <span data-ttu-id="25708-114">La modalità di recupero dei server nel nuovo hardware.</span><span class="sxs-lookup"><span data-stu-id="25708-114">How you will recover servers on new hardware.</span></span>

  - <span data-ttu-id="25708-115">La modalità di recupero dei servizi per i quali è necessario l'intervento di più aree aziendali o reparti.</span><span class="sxs-lookup"><span data-stu-id="25708-115">How you will recover services that require action on the part of multiple business areas or departments.</span></span>

  - <span data-ttu-id="25708-116">La modalità di acquisizione rapida di server di riserva.</span><span class="sxs-lookup"><span data-stu-id="25708-116">How you can acquire spare servers quickly.</span></span>

  - <span data-ttu-id="25708-117">Il tempo necessario per il ripristino secondo la strategia in questione</span><span class="sxs-lookup"><span data-stu-id="25708-117">The time it takes to recover by using your strategy.</span></span> <span data-ttu-id="25708-118">Considerare i requisiti dell'organizzazione per l'obiettivo del tempo di ripristino (RTO).</span><span class="sxs-lookup"><span data-stu-id="25708-118">Consider your organization’s requirements for recovery time objective (RTO).</span></span>

<span data-ttu-id="25708-119">Modificare le procedure di backup e ripristino in questo argomento, aggiungendo ed eliminando le procedure appropriate, in modo da riflettere i server e i componenti della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="25708-119">Modify the backup and restoration procedures in this topic, adding and deleting procedures as appropriate, to reflect the servers and components in your deployment.</span></span> <span data-ttu-id="25708-120">È inoltre possibile aggiungere informazioni appropriate, ad esempio la pianificazione di backup, alle procedure appropriate per assicurarsi che le informazioni non vengano trascurate.</span><span class="sxs-lookup"><span data-stu-id="25708-120">You can also add appropriate details, such as the backup schedule, to the appropriate procedures to make sure that the information is not overlooked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25708-121">È consigliabile creare script per il maggior numero possibile di passaggi, per garantire la qualità e la riproducibilità delle procedure.</span><span class="sxs-lookup"><span data-stu-id="25708-121">It is good practice to create scripts for as many steps as possible, to help ensure the quality and reproducibility of procedures.</span></span>



</div>

<span data-ttu-id="25708-122">Nel piano specificare chi è responsabile della revisione del piano, che è responsabile del testing e della convalida di qualsiasi nuova procedura o strumento e che deve approvare le modifiche apportate al piano e alle relative procedure.</span><span class="sxs-lookup"><span data-stu-id="25708-122">In your plan, specify who is responsible for reviewing the plan, who is responsible for testing and validating any new procedures or tools, and who must approve any changes to the plan and related procedures.</span></span>

<span data-ttu-id="25708-123">Per assicurarsi che il piano di backup e ripristino soddisfi pienamente tutti gli obiettivi e le priorità stabiliti, ottenere l'approvazione dei responsabili decisionali e delle decisioni tecniche aziendali appropriate nell'organizzazione prima di implementare il piano.</span><span class="sxs-lookup"><span data-stu-id="25708-123">To make sure that your backup and restoration plan fully meets all established goals and priorities, get the approval of the appropriate business decision makers and technical decision makers in your organization before you implement the plan.</span></span>

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a><span data-ttu-id="25708-124">Implementazione del piano di backup e ripristino</span><span class="sxs-lookup"><span data-stu-id="25708-124">Implementing the Backup and Restoration Plan</span></span>

<span data-ttu-id="25708-125">L'implementazione di un piano di backup e ripristino richiede i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="25708-125">Implementing a backup and restoration plan requires the following steps:</span></span>

  - <span data-ttu-id="25708-126">Test e convalida del piano.</span><span class="sxs-lookup"><span data-stu-id="25708-126">Testing and validating the plan.</span></span>

  - <span data-ttu-id="25708-127">Comunicazione del piano.</span><span class="sxs-lookup"><span data-stu-id="25708-127">Communicating the plan.</span></span>

  - <span data-ttu-id="25708-128">Convalida delle operazioni di backup e ripristino.</span><span class="sxs-lookup"><span data-stu-id="25708-128">Validating backup and restoration operations.</span></span>

<div>

## <a name="testing-and-validating-the-plan"></a><span data-ttu-id="25708-129">Test e convalida del piano</span><span class="sxs-lookup"><span data-stu-id="25708-129">Testing and Validating the Plan</span></span>

<span data-ttu-id="25708-130">Le procedure descritte in questo articolo sono state testate e convalidate in un ambiente lab.</span><span class="sxs-lookup"><span data-stu-id="25708-130">The procedures described here have been tested and validated in a lab environment.</span></span> <span data-ttu-id="25708-131">Per assicurarsi che queste o altre procedure funzionino nell'ambiente in uso, è consigliabile testare e convalidare ogni procedura che si intende implementare.</span><span class="sxs-lookup"><span data-stu-id="25708-131">To make sure that these or any other procedures work in your environment, you should test and validate each procedure you intend to implement.</span></span> <span data-ttu-id="25708-132">Completare i test e la convalida prima di inviare il piano per l'approvazione finale.</span><span class="sxs-lookup"><span data-stu-id="25708-132">Complete the testing and the validation before you submit your plan for final approval.</span></span>

</div>

<div>

## <a name="communicating-the-plan"></a><span data-ttu-id="25708-133">Comunicazione del piano</span><span class="sxs-lookup"><span data-stu-id="25708-133">Communicating the Plan</span></span>

<span data-ttu-id="25708-134">Il piano di backup e ripristino deve descrivere chiaramente chi implementa le procedure e le istruzioni dettagliate per l'esecuzione delle procedure.</span><span class="sxs-lookup"><span data-stu-id="25708-134">Your backup and restoration plan should clearly describe who implements procedures and step-by-step instructions for carrying out the procedures.</span></span> <span data-ttu-id="25708-135">È necessario assicurarsi che tutti i responsabili di qualsiasi aspetto del backup e del ripristino comprendano il piano, il modo in cui deve essere implementato e il relativo ruolo.</span><span class="sxs-lookup"><span data-stu-id="25708-135">You should make sure that everyone responsible for any aspect of backup and restoration understands the plan, how it is to be implemented, and what their role is.</span></span> <span data-ttu-id="25708-136">Sono inclusi tutti i requisiti di implementazione per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="25708-136">This includes all implementation requirements for the following:</span></span>

  - <span data-ttu-id="25708-137">Backup del pool e del server.</span><span class="sxs-lookup"><span data-stu-id="25708-137">Pool and server backup.</span></span>

  - <span data-ttu-id="25708-138">Ripristino del servizio.</span><span class="sxs-lookup"><span data-stu-id="25708-138">Restoration of service.</span></span>

<span data-ttu-id="25708-139">**Backup di pool e server**</span><span class="sxs-lookup"><span data-stu-id="25708-139">**Pool and server backup**</span></span>

<span data-ttu-id="25708-p106">Nel piano di backup e ripristino devono essere disponibili tutte le informazioni necessarie per l'esecuzione delle procedure di backup con regolarità costante. Le informazioni principali da comunicare ai membri del team dei responsabili sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="25708-p106">The backup and restoration plan should include all information required to complete backup procedures on an ongoing basis. The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="25708-142">Team o Person (specificato come singolo o ruolo) responsabile del backup di ogni server.</span><span class="sxs-lookup"><span data-stu-id="25708-142">Team or person (specified as an individual or role) responsible for backing up each server.</span></span>

  - <span data-ttu-id="25708-143">Pianificazioni specifiche per il backup di ogni server.</span><span class="sxs-lookup"><span data-stu-id="25708-143">Specific schedules for backing up each server.</span></span>

  - <span data-ttu-id="25708-144">Percorsi di backup per ogni tipo di dati (impostazioni, database e condivisioni di file).</span><span class="sxs-lookup"><span data-stu-id="25708-144">Backup locations for each type of data (settings, database, and file shares).</span></span>

  - <span data-ttu-id="25708-145">Procedure di backup da utilizzare, compresi gli strumenti necessari per il completamento di ogni procedura.</span><span class="sxs-lookup"><span data-stu-id="25708-145">Backup procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="25708-146">Informazioni necessarie per completare i backup, come indicato nei [fogli di lavoro per il backup e il ripristino di Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="25708-146">Information required to complete backups, as covered in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="25708-147">Metodi di convalida da utilizzare per garantire che i dati e le impostazioni siano adeguatamente sottoposti a backup e disponibili per il ripristino, che possono includere controlli periodici e ripristini dei test.</span><span class="sxs-lookup"><span data-stu-id="25708-147">Validation methods to be used to help ensure that data and settings are appropriately backed up and available for restoration, which can include periodic audits and test restorations.</span></span>

<span data-ttu-id="25708-148">**Ripristino del servizio**</span><span class="sxs-lookup"><span data-stu-id="25708-148">**Restoration of service**</span></span>

<span data-ttu-id="25708-149">Il piano di backup e ripristino deve includere tutte le informazioni necessarie per il ripristino del servizio, nel caso in cui uno o più server verifichino una perdita che rende il servizio non disponibile.</span><span class="sxs-lookup"><span data-stu-id="25708-149">The backup and restoration plan should include all information required to restore service, in case one or more servers experience a loss that makes service unavailable.</span></span> <span data-ttu-id="25708-150">Le informazioni principali da comunicare ai membri del team dei responsabili sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="25708-150">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="25708-151">Team o persona (individuo o ruolo) responsabile di determinare quando è necessario il ripristino del servizio e le procedure da utilizzare per il ripristino, nonché il team o la persona responsabile dell'implementazione delle procedure per ogni scenario di ripristino.</span><span class="sxs-lookup"><span data-stu-id="25708-151">Team or person (specified as an individual or a role) that is responsible for determining when restoration of service is required and the procedures to be used to restore service, and also the team or person responsible for implementing procedures for each restoration scenario.</span></span>

  - <span data-ttu-id="25708-152">Criteri per stabilire le procedure di ripristino più appropriate per una situazione specifica.</span><span class="sxs-lookup"><span data-stu-id="25708-152">Criteria for determining which restoration procedures are most appropriate for a specific situation.</span></span>

  - <span data-ttu-id="25708-153">Stime temporali per il ripristino dell'obiettivo del tempo di ripristino e del servizio (RTO) in ogni scenario di ripristino.</span><span class="sxs-lookup"><span data-stu-id="25708-153">Time estimates for restoration of service and recovery time objective (RTO) in each restoration scenario.</span></span>

  - <span data-ttu-id="25708-154">Procedure di ripristino da seguire e strumenti necessari per l'esecuzione di ogni procedura.</span><span class="sxs-lookup"><span data-stu-id="25708-154">Restoration procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="25708-155">Informazioni necessarie per il ripristino di dati e impostazioni.</span><span class="sxs-lookup"><span data-stu-id="25708-155">Information required to restore data and settings.</span></span> <span data-ttu-id="25708-156">I fogli di lavoro vengono forniti nei fogli di lavoro [per il backup e il ripristino di Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="25708-156">Worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a><span data-ttu-id="25708-157">Convalida delle operazioni di backup e ripristino</span><span class="sxs-lookup"><span data-stu-id="25708-157">Validating Backup and Restoration Operations</span></span>

<span data-ttu-id="25708-158">Dopo aver eseguito le operazioni di backup iniziali nell'ambiente di produzione a intervalli specifici, secondo quanto indicato nel piano di backup e ripristino, è necessario verificare che:</span><span class="sxs-lookup"><span data-stu-id="25708-158">After completing initial backup efforts in your production environment and at specified intervals (as covered in your backup and restoration plan), you should verify the following:</span></span>

  - <span data-ttu-id="25708-159">Il backup venga eseguito come richiesto.</span><span class="sxs-lookup"><span data-stu-id="25708-159">Backups are occurring as required.</span></span>

  - <span data-ttu-id="25708-160">I dati e le impostazioni di backup sono accessibili.</span><span class="sxs-lookup"><span data-stu-id="25708-160">Backed-up data and settings are accessible.</span></span>

  - <span data-ttu-id="25708-161">Le procedure di ripristino possono essere eseguite entro gli orari degli obiettivi del tempo di ripristino (RTO) specificati nel piano di backup e ripristino e i risultati soddisfano tutti i requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="25708-161">Restoration procedures can be performed within the recovery time objective (RTO) times specified in the backup and restoration plan, and the results meet all business requirements.</span></span>

  - <span data-ttu-id="25708-162">I fogli di lavoro di backup siano stati compilati, verificati e archiviati in un luogo sicuro.</span><span class="sxs-lookup"><span data-stu-id="25708-162">Backup worksheets have been completed and verified, and they are stored in a secure location.</span></span> <span data-ttu-id="25708-163">Questi fogli di lavoro sono disponibili nei fogli di lavoro di [backup e ripristino per Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="25708-163">These worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="25708-164">Il funzionamento delle procedure di ripristino sia stato sottoposto a test e verificato come previsto, in base a quanto specificato nel piano di backup e ripristino.</span><span class="sxs-lookup"><span data-stu-id="25708-164">Restoration procedures have been tested and verified to work as expected, as specified in your backup and restoration plan.</span></span>

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a><span data-ttu-id="25708-165">Gestione del piano di backup e ripristino</span><span class="sxs-lookup"><span data-stu-id="25708-165">Maintaining the Backup and Restoration Plan</span></span>

<span data-ttu-id="25708-166">Una topologia di Lync Server è un ambiente dinamico che cambia con l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="25708-166">A Lync Server topology is a dynamic environment that changes with your organization.</span></span> <span data-ttu-id="25708-167">Rivalutare il piano di backup e ripristino come cambia l'organizzazione e rivederlo periodicamente per assicurarsi che continui a soddisfare le esigenze della propria azienda.</span><span class="sxs-lookup"><span data-stu-id="25708-167">Reassess your backup and restoration plan as your organization changes, and review it periodically to make sure that it continues to meet the needs of your business.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

