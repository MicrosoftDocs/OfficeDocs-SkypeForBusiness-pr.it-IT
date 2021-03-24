---
title: Preparare la foresta corrente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: Per preparare la foresta di Servizi di dominio Active Directory, è necessario estendere correttamente lo schema, come descritto nell'argomento Running Schema Preparation, e verificare che lo schema sia stato replicato.
ms.openlocfilehash: 3a143ebc58fe14712c194abb18eb9de98c2ca2cb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097322"
---
# <a name="prepare-current-forest"></a><span data-ttu-id="9a73d-103">Preparare la foresta corrente</span><span class="sxs-lookup"><span data-stu-id="9a73d-103">Prepare Current Forest</span></span>

<span data-ttu-id="9a73d-104">Per preparare la foresta di Servizi di dominio Active Directory, è necessario estendere correttamente lo schema, come descritto nell'argomento [Running Schema Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema)e verificare che lo schema sia stato replicato.</span><span class="sxs-lookup"><span data-stu-id="9a73d-104">To prepare the Active Directory Domain Services forest, you must successfully extend the schema, as described in the topic [Running Schema Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema), and make sure that the schema has replicated.</span></span>

<span data-ttu-id="9a73d-p101">Dopo aver completato queste operazioni prerequisite, è possibile iniziare con il **Passaggio 3: Preparazione della foresta corrente**. Per preparare la foresta, eseguire l'accesso a un computer nella radice della foresta come membri del gruppo Domain Admins in tale radice o come membri del gruppo Enterprise Admins per la foresta che si sta preparando.</span><span class="sxs-lookup"><span data-stu-id="9a73d-p101">After completing these prerequisites, you can begin **Step 3: Prepare Current Forest**. To prepare the forest, log on to a computer in the forest root as a member of Domain Admins in the forest root, or as a member of the Enterprise Admins for the forest that you are preparing.</span></span>

1. <span data-ttu-id="9a73d-107">Dal **Passaggio 3: Preparazione della foresta corrente** della Distribuzione guidata, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="9a73d-107">From the Deployment Wizard at **Step 3: Prepare Current Forest**, click **Run**.</span></span>

2. <span data-ttu-id="9a73d-108">Nella pagina **Prepara foresta** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9a73d-108">From the **Prepare Forest** page, click **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9a73d-109">La preparazione della foresta consente di scegliere dove posizionare i gruppi universali per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9a73d-109">Forest Preparation enables you to choose where to place the Universal Groups for Skype for Business Server.</span></span> <span data-ttu-id="9a73d-110">Scegliere una posizione conforme ai requisiti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a73d-110">Choose a location that is consistent with the requirements of your organization.</span></span>

3. <span data-ttu-id="9a73d-p103">Nella pagina **Esecuzione comandi in corso** ricercare **Stato attività: Operazione completata** e quindi fare clic su **Visualizza registro**. Verificare che non vi siano errori. Esaminare gli avvisi per stabilire se siano previsti e normali per l'infrastruttura di cui si dispone.</span><span class="sxs-lookup"><span data-stu-id="9a73d-p103">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**. Make sure that there are no errors. Review the warnings to determine if they are expected and typical for your infrastructure.</span></span>

4. <span data-ttu-id="9a73d-114">Nella colonna **Azione** del registro espandere **Forest Prep,** cercare un risultato di esecuzione alla fine di ogni attività per verificare che la preparazione della foresta sia stata completata correttamente, chiudere il registro e quindi fare clic **\<Success\>** su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="9a73d-114">Under the **Action** column in the log, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

5. <span data-ttu-id="9a73d-115">Attendere il completamento della replica di Servizi di dominio Active Directory o forzare la replica in tutti i controller di dominio elencati nello snap-in Siti e servizi di **Active Directory** per il controller di dominio radice della foresta, prima di eseguire la preparazione del dominio.</span><span class="sxs-lookup"><span data-stu-id="9a73d-115">Wait for Active Directory Domain Services replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span> <span data-ttu-id="9a73d-116">Forzare la replica tra i controller di dominio in tutti i siti di Active Directory perché la replica all'interno dei siti venga eseguita entro pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="9a73d-116">Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

    > [!TIP]
    > <span data-ttu-id="9a73d-117">Se è necessario esaminare i file di registro creati dalla Distribuzione guidata di Skype for Business Server, è possibile trovarli nel computer in cui è stata eseguita la Distribuzione guidata, nella directory Utenti dell'utente di Servizi di dominio Active Directory che ha eseguito il passaggio.</span><span class="sxs-lookup"><span data-stu-id="9a73d-117">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="9a73d-118">Ad esempio, se l'utente ha eseguito l'accesso come amministratore di dominio nel Contoso.net di dominio, i file di registro si trovano in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="9a73d-118">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span>