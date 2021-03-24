---
title: Preparare il dominio corrente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: "Per preparare un dominio per ospitare server che eseguono utenti di Skype for Business Server o Skype for Business Server, è necessario completare Passaggio 5: Preparare il dominio corrente, come descritto nell'argomento Using Setup to Run Domain Preparation. Per poter completare tale passaggio, è necessario essere connessi come membri del gruppo Domain Admins nel dominio che si sta preparando oppure come membri del gruppo Enterprise Admins della foresta a cui appartiene il dominio. Per preparare il dominio, eseguire le operazioni seguenti:"
ms.openlocfilehash: a71e50b0f3d55709c3c22709177b41e541f7075f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097341"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="70823-105">Preparare il dominio corrente</span><span class="sxs-lookup"><span data-stu-id="70823-105">Prepare Current Domain</span></span>

<span data-ttu-id="70823-106">Per preparare un dominio per ospitare server che eseguono Utenti di Skype for Business Server o Skype for Business Server, è necessario completare **passaggio 5: Preparare** il dominio corrente, come descritto nell'argomento Utilizzo del programma di installazione per eseguire la preparazione [del dominio.](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation)</span><span class="sxs-lookup"><span data-stu-id="70823-106">To prepare a domain to host servers running Skype for Business Server or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation).</span></span> <span data-ttu-id="70823-107">Per poter completare tale passaggio, è necessario essere connessi come membri del gruppo Domain Admins nel dominio che si sta preparando oppure come membri del gruppo Enterprise Admins della foresta a cui appartiene il dominio.</span><span class="sxs-lookup"><span data-stu-id="70823-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="70823-108">Per preparare il dominio, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="70823-108">To prepare the domain:</span></span>

1. <span data-ttu-id="70823-109">Dalla cartella o dal supporto di installazione di Skype for Business Server, eseguire Setup.exe per avviare la Distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="70823-109">From the Skype for Business Server installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="70823-110">Fare clic su **Prepara Active Directory** e quindi attendere che venga determinato lo stato della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="70823-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="70823-111">Al **Passaggio 5: Preparazione del dominio corrente**, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="70823-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="70823-112">Nella pagina **Esecuzione comandi in corso** ricercare **Stato attività: Operazione completata** e quindi fare clic su **Visualizza registro**.</span><span class="sxs-lookup"><span data-stu-id="70823-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="70823-113">Nella colonna **Azione** espandere **Domain Prep**, cercare un risultato di esecuzione alla fine di ogni attività per verificare che la preparazione del dominio sia stata completata correttamente, chiudere il registro e quindi fare clic **\<Success\>** su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="70823-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="70823-114">Se è necessario esaminare i file di registro creati dalla Distribuzione guidata di Skype for Business Server, è possibile trovarli nel computer in cui è stata eseguita la Distribuzione guidata nella directory Utenti dell'utente di Servizi di dominio Active Directory che ha eseguito il passaggio.</span><span class="sxs-lookup"><span data-stu-id="70823-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="70823-115">Ad esempio, se l'utente ha eseguito l'accesso come amministratore di dominio nel Contoso.net di dominio, i file di registro si trovano in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span><span class="sxs-lookup"><span data-stu-id="70823-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>