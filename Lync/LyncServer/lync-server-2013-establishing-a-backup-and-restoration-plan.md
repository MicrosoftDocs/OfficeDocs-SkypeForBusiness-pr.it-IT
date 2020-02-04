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
ms.openlocfilehash: cee1c4571dafa4e513f42613de13205ecec9de42
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a><span data-ttu-id="05f23-102">Creazione di un piano di backup e ripristino per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05f23-102">Establishing a backup and restoration plan for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05f23-103">_**Argomento Ultima modifica:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="05f23-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="05f23-104">La creazione di un piano di backup e ripristino prevede i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="05f23-104">Creating a backup and restoration plan involves the following steps:</span></span>

  - <span data-ttu-id="05f23-105">Sviluppo del piano.</span><span class="sxs-lookup"><span data-stu-id="05f23-105">Developing the plan.</span></span>

  - <span data-ttu-id="05f23-106">Implementazione del piano.</span><span class="sxs-lookup"><span data-stu-id="05f23-106">Implementing the plan.</span></span>

  - <span data-ttu-id="05f23-107">Manutenzione del piano.</span><span class="sxs-lookup"><span data-stu-id="05f23-107">Maintaining the plan.</span></span>

<div>

## <a name="developing-a-backup-and-restoration-plan"></a><span data-ttu-id="05f23-108">Sviluppo di un piano di backup e ripristino</span><span class="sxs-lookup"><span data-stu-id="05f23-108">Developing a Backup and Restoration Plan</span></span>

<span data-ttu-id="05f23-109">Dopo aver sviluppato la strategia di backup e ripristino per Lync Server, è possibile usarla per documentare un piano di backup e ripristino dettagliato.</span><span class="sxs-lookup"><span data-stu-id="05f23-109">After you develop your backup and restoration strategy for Lync Server, use it to document a detailed backup and restoration plan.</span></span> <span data-ttu-id="05f23-110">Il piano deve trasmettere chiaramente le priorità e i requisiti per il backup dei dati e delle impostazioni.</span><span class="sxs-lookup"><span data-stu-id="05f23-110">Your plan should clearly convey the priorities and requirements for backing up data and settings.</span></span> <span data-ttu-id="05f23-111">È possibile usare le informazioni disponibili per [stabilire una strategia di backup e ripristino per Lync server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) e i fogli di lavoro in fogli di lavoro di [backup e ripristino per Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) per facilitare la documentazione della propria strategia.</span><span class="sxs-lookup"><span data-stu-id="05f23-111">You can use the information in [Establishing a backup and restoration strategy for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) and the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) to facilitate the documentation of your strategy.</span></span> <span data-ttu-id="05f23-112">Il piano deve inoltre contenere criteri per decidere quando e come ripristinare il servizio.</span><span class="sxs-lookup"><span data-stu-id="05f23-112">Your plan should also contain criteria for deciding when and how to restore service.</span></span>

<span data-ttu-id="05f23-113">Man mano che sviluppi il piano, devi prendere in considerazione e tenere conto di quanto segue:</span><span class="sxs-lookup"><span data-stu-id="05f23-113">As you develop your plan, you need to consider, and account for, the following:</span></span>

  - <span data-ttu-id="05f23-114">Come ripristinare i server nel nuovo hardware.</span><span class="sxs-lookup"><span data-stu-id="05f23-114">How you will recover servers on new hardware.</span></span>

  - <span data-ttu-id="05f23-115">Come si recupereranno i servizi che richiedono un'azione da parte di più aree o reparti aziendali.</span><span class="sxs-lookup"><span data-stu-id="05f23-115">How you will recover services that require action on the part of multiple business areas or departments.</span></span>

  - <span data-ttu-id="05f23-116">Come è possibile acquisire rapidamente i server di riserva.</span><span class="sxs-lookup"><span data-stu-id="05f23-116">How you can acquire spare servers quickly.</span></span>

  - <span data-ttu-id="05f23-117">Il tempo necessario per il ripristino usando la strategia.</span><span class="sxs-lookup"><span data-stu-id="05f23-117">The time it takes to recover by using your strategy.</span></span> <span data-ttu-id="05f23-118">Considera i requisiti dell'organizzazione per l'obiettivo del tempo di recupero (RTO).</span><span class="sxs-lookup"><span data-stu-id="05f23-118">Consider your organization’s requirements for recovery time objective (RTO).</span></span>

<span data-ttu-id="05f23-119">Modificare le procedure di backup e ripristino in questo argomento, aggiungendo ed eliminando le procedure appropriate per riflettere i server e i componenti della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="05f23-119">Modify the backup and restoration procedures in this topic, adding and deleting procedures as appropriate, to reflect the servers and components in your deployment.</span></span> <span data-ttu-id="05f23-120">È anche possibile aggiungere dettagli appropriati, ad esempio la pianificazione del backup, alle procedure appropriate per verificare che le informazioni non vengano trascurate.</span><span class="sxs-lookup"><span data-stu-id="05f23-120">You can also add appropriate details, such as the backup schedule, to the appropriate procedures to make sure that the information is not overlooked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="05f23-121">È buona norma creare script per il maggior numero possibile di passaggi, per garantire la qualità e la riproducibilità delle procedure.</span><span class="sxs-lookup"><span data-stu-id="05f23-121">It is good practice to create scripts for as many steps as possible, to help ensure the quality and reproducibility of procedures.</span></span>



</div>

<span data-ttu-id="05f23-122">Nel piano specificare chi è responsabile della revisione del piano, che è responsabile del test e della convalida di eventuali nuove procedure o strumenti e che deve approvare le eventuali modifiche apportate al piano e alle procedure correlate.</span><span class="sxs-lookup"><span data-stu-id="05f23-122">In your plan, specify who is responsible for reviewing the plan, who is responsible for testing and validating any new procedures or tools, and who must approve any changes to the plan and related procedures.</span></span>

<span data-ttu-id="05f23-123">Per assicurarti che il piano di backup e ripristino soddisfi pienamente tutti gli obiettivi e le priorità stabiliti, Ottieni l'approvazione dei responsabili decisionali e delle decisioni tecniche aziendali appropriate prima di implementare il piano.</span><span class="sxs-lookup"><span data-stu-id="05f23-123">To make sure that your backup and restoration plan fully meets all established goals and priorities, get the approval of the appropriate business decision makers and technical decision makers in your organization before you implement the plan.</span></span>

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a><span data-ttu-id="05f23-124">Implementazione del piano di backup e ripristino</span><span class="sxs-lookup"><span data-stu-id="05f23-124">Implementing the Backup and Restoration Plan</span></span>

<span data-ttu-id="05f23-125">L'implementazione di un piano di backup e ripristino richiede i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="05f23-125">Implementing a backup and restoration plan requires the following steps:</span></span>

  - <span data-ttu-id="05f23-126">Testare e convalidare il piano.</span><span class="sxs-lookup"><span data-stu-id="05f23-126">Testing and validating the plan.</span></span>

  - <span data-ttu-id="05f23-127">Comunicare il piano.</span><span class="sxs-lookup"><span data-stu-id="05f23-127">Communicating the plan.</span></span>

  - <span data-ttu-id="05f23-128">Convalida delle operazioni di backup e ripristino.</span><span class="sxs-lookup"><span data-stu-id="05f23-128">Validating backup and restoration operations.</span></span>

<div>

## <a name="testing-and-validating-the-plan"></a><span data-ttu-id="05f23-129">Test e convalida del piano</span><span class="sxs-lookup"><span data-stu-id="05f23-129">Testing and Validating the Plan</span></span>

<span data-ttu-id="05f23-130">Le procedure descritte in questo articolo sono state testate e convalidate in un ambiente lab.</span><span class="sxs-lookup"><span data-stu-id="05f23-130">The procedures described here have been tested and validated in a lab environment.</span></span> <span data-ttu-id="05f23-131">Per assicurarsi che queste o altre procedure funzionino nell'ambiente, è consigliabile testare e convalidare ogni procedura da implementare.</span><span class="sxs-lookup"><span data-stu-id="05f23-131">To make sure that these or any other procedures work in your environment, you should test and validate each procedure you intend to implement.</span></span> <span data-ttu-id="05f23-132">Completare i test e la convalida prima di inviare il piano per l'approvazione finale.</span><span class="sxs-lookup"><span data-stu-id="05f23-132">Complete the testing and the validation before you submit your plan for final approval.</span></span>

</div>

<div>

## <a name="communicating-the-plan"></a><span data-ttu-id="05f23-133">Comunicare il piano</span><span class="sxs-lookup"><span data-stu-id="05f23-133">Communicating the Plan</span></span>

<span data-ttu-id="05f23-134">Il piano di backup e ripristino deve descrivere chiaramente chi implementa le procedure e le istruzioni dettagliate per l'esecuzione delle procedure.</span><span class="sxs-lookup"><span data-stu-id="05f23-134">Your backup and restoration plan should clearly describe who implements procedures and step-by-step instructions for carrying out the procedures.</span></span> <span data-ttu-id="05f23-135">È necessario assicurarsi che tutti i responsabili di qualsiasi aspetto del backup e del ripristino comprendano il piano, il modo in cui devono essere implementati e il loro ruolo.</span><span class="sxs-lookup"><span data-stu-id="05f23-135">You should make sure that everyone responsible for any aspect of backup and restoration understands the plan, how it is to be implemented, and what their role is.</span></span> <span data-ttu-id="05f23-136">Include tutti i requisiti di implementazione per i seguenti:</span><span class="sxs-lookup"><span data-stu-id="05f23-136">This includes all implementation requirements for the following:</span></span>

  - <span data-ttu-id="05f23-137">Backup di pool e server.</span><span class="sxs-lookup"><span data-stu-id="05f23-137">Pool and server backup.</span></span>

  - <span data-ttu-id="05f23-138">Ripristino del servizio.</span><span class="sxs-lookup"><span data-stu-id="05f23-138">Restoration of service.</span></span>

<span data-ttu-id="05f23-139">**Backup di pool e server**</span><span class="sxs-lookup"><span data-stu-id="05f23-139">**Pool and server backup**</span></span>

<span data-ttu-id="05f23-140">Il piano di backup e ripristino deve includere tutte le informazioni necessarie per completare le procedure di backup su base continuativa.</span><span class="sxs-lookup"><span data-stu-id="05f23-140">The backup and restoration plan should include all information required to complete backup procedures on an ongoing basis.</span></span> <span data-ttu-id="05f23-141">Le informazioni principali da comunicare ai membri del team responsabili includono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="05f23-141">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="05f23-142">Team o Person (specificato come singolo o ruolo) responsabile del backup di ogni server.</span><span class="sxs-lookup"><span data-stu-id="05f23-142">Team or person (specified as an individual or role) responsible for backing up each server.</span></span>

  - <span data-ttu-id="05f23-143">Pianificazioni specifiche per il backup di ogni server.</span><span class="sxs-lookup"><span data-stu-id="05f23-143">Specific schedules for backing up each server.</span></span>

  - <span data-ttu-id="05f23-144">Percorsi di backup per ogni tipo di dati (impostazioni, database e condivisioni di file).</span><span class="sxs-lookup"><span data-stu-id="05f23-144">Backup locations for each type of data (settings, database, and file shares).</span></span>

  - <span data-ttu-id="05f23-145">Procedure di backup da usare, inclusi gli strumenti necessari per completare ogni procedura.</span><span class="sxs-lookup"><span data-stu-id="05f23-145">Backup procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="05f23-146">Informazioni necessarie per completare i backup, come descritto in fogli di lavoro di [backup e ripristino per Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="05f23-146">Information required to complete backups, as covered in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="05f23-147">Metodi di convalida da usare per verificare che i dati e le impostazioni siano opportunamente sostenuti e disponibili per il ripristino, che può includere controlli periodici e ripristini di test.</span><span class="sxs-lookup"><span data-stu-id="05f23-147">Validation methods to be used to help ensure that data and settings are appropriately backed up and available for restoration, which can include periodic audits and test restorations.</span></span>

<span data-ttu-id="05f23-148">**Ripristino del servizio**</span><span class="sxs-lookup"><span data-stu-id="05f23-148">**Restoration of service**</span></span>

<span data-ttu-id="05f23-149">Il piano di backup e ripristino deve includere tutte le informazioni necessarie per il ripristino del servizio, nel caso in cui uno o più server verifichino una perdita che rende il servizio non disponibile.</span><span class="sxs-lookup"><span data-stu-id="05f23-149">The backup and restoration plan should include all information required to restore service, in case one or more servers experience a loss that makes service unavailable.</span></span> <span data-ttu-id="05f23-150">Le informazioni principali da comunicare ai membri del team responsabili includono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="05f23-150">The primary information to be communicated to responsible team members includes the following:</span></span>

  - <span data-ttu-id="05f23-151">Team o Person (specificato come un singolo o un ruolo) responsabile per determinare quando è necessario il ripristino del servizio e le procedure da usare per ripristinare il servizio e anche il team o la persona responsabile dell'implementazione delle procedure per ogni scenario di ripristino.</span><span class="sxs-lookup"><span data-stu-id="05f23-151">Team or person (specified as an individual or a role) that is responsible for determining when restoration of service is required and the procedures to be used to restore service, and also the team or person responsible for implementing procedures for each restoration scenario.</span></span>

  - <span data-ttu-id="05f23-152">Criteri per determinare quali procedure di ripristino sono più appropriate per una specifica situazione.</span><span class="sxs-lookup"><span data-stu-id="05f23-152">Criteria for determining which restoration procedures are most appropriate for a specific situation.</span></span>

  - <span data-ttu-id="05f23-153">Stime temporali per il ripristino dell'obiettivo del tempo di servizio e di ripristino (RTO) in ogni scenario di ripristino.</span><span class="sxs-lookup"><span data-stu-id="05f23-153">Time estimates for restoration of service and recovery time objective (RTO) in each restoration scenario.</span></span>

  - <span data-ttu-id="05f23-154">Procedure di ripristino da usare, inclusi gli strumenti necessari per completare ogni procedura.</span><span class="sxs-lookup"><span data-stu-id="05f23-154">Restoration procedures to be used, including the tools required to complete each procedure.</span></span>

  - <span data-ttu-id="05f23-155">Informazioni necessarie per ripristinare dati e impostazioni.</span><span class="sxs-lookup"><span data-stu-id="05f23-155">Information required to restore data and settings.</span></span> <span data-ttu-id="05f23-156">I fogli di lavoro sono disponibili in fogli di lavoro di [backup e ripristino per Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="05f23-156">Worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a><span data-ttu-id="05f23-157">Convalida delle operazioni di backup e ripristino</span><span class="sxs-lookup"><span data-stu-id="05f23-157">Validating Backup and Restoration Operations</span></span>

<span data-ttu-id="05f23-158">Dopo aver completato gli sforzi iniziali di backup nell'ambiente di produzione e a intervalli specificati, come descritto nel piano di backup e ripristino, è necessario verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="05f23-158">After completing initial backup efforts in your production environment and at specified intervals (as covered in your backup and restoration plan), you should verify the following:</span></span>

  - <span data-ttu-id="05f23-159">I backup si verificano come richiesto.</span><span class="sxs-lookup"><span data-stu-id="05f23-159">Backups are occurring as required.</span></span>

  - <span data-ttu-id="05f23-160">I dati e le impostazioni di cui è stato eseguito il backup sono accessibili.</span><span class="sxs-lookup"><span data-stu-id="05f23-160">Backed-up data and settings are accessible.</span></span>

  - <span data-ttu-id="05f23-161">Le procedure di ripristino possono essere eseguite entro gli orari di recupero degli obiettivi temporali (RTO) specificati nel piano di backup e ripristino e i risultati soddisfano tutti i requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="05f23-161">Restoration procedures can be performed within the recovery time objective (RTO) times specified in the backup and restoration plan, and the results meet all business requirements.</span></span>

  - <span data-ttu-id="05f23-162">I fogli di lavoro di backup sono stati completati e verificati e archiviati in una posizione sicura.</span><span class="sxs-lookup"><span data-stu-id="05f23-162">Backup worksheets have been completed and verified, and they are stored in a secure location.</span></span> <span data-ttu-id="05f23-163">Questi fogli di lavoro sono disponibili in fogli di lavoro di [backup e ripristino per Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span><span class="sxs-lookup"><span data-stu-id="05f23-163">These worksheets are provided in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).</span></span>

  - <span data-ttu-id="05f23-164">Le procedure di ripristino sono state testate e verificate per funzionare come previsto, come specificato nel piano di backup e ripristino.</span><span class="sxs-lookup"><span data-stu-id="05f23-164">Restoration procedures have been tested and verified to work as expected, as specified in your backup and restoration plan.</span></span>

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a><span data-ttu-id="05f23-165">Manutenzione del piano di backup e ripristino</span><span class="sxs-lookup"><span data-stu-id="05f23-165">Maintaining the Backup and Restoration Plan</span></span>

<span data-ttu-id="05f23-166">Una topologia di Lync Server è un ambiente dinamico che viene modificato con l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="05f23-166">A Lync Server topology is a dynamic environment that changes with your organization.</span></span> <span data-ttu-id="05f23-167">Rivalutare il piano di backup e ripristino Man mano che l'organizzazione cambia e rivederla periodicamente per verificare che continui a soddisfare le esigenze della propria azienda.</span><span class="sxs-lookup"><span data-stu-id="05f23-167">Reassess your backup and restoration plan as your organization changes, and review it periodically to make sure that it continues to meet the needs of your business.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

