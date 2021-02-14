---
title: Preparare il dominio corrente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: "Per preparare un dominio per ospitare server che eseguono utenti di Skype for Business Server 2015 o Skype for Business Server, è necessario completare il passaggio 5: Preparare il dominio corrente, come descritto nell'argomento Utilizzo del programma di installazione per eseguire la preparazione del dominio. Per poter completare tale passaggio, è necessario essere connessi come membri del gruppo Domain Admins nel dominio che si sta preparando oppure come membri del gruppo Enterprise Admins della foresta a cui appartiene il dominio. Per preparare il dominio, eseguire le operazioni seguenti:"
ms.openlocfilehash: b43af552983a5a7aae998fab6de9ace4e96084b2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804966"
---
# <a name="prepare-current-domain"></a><span data-ttu-id="62ddd-105">Preparare il dominio corrente</span><span class="sxs-lookup"><span data-stu-id="62ddd-105">Prepare Current Domain</span></span>

<span data-ttu-id="62ddd-106">Per preparare un dominio per ospitare server che eseguono utenti di Skype for Business Server 2015 o Skype for Business Server, è necessario completare il passaggio **5: Preparare** il dominio corrente, come descritto nell'argomento Utilizzo del programma di installazione per eseguire la preparazione del [dominio.](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)</span><span class="sxs-lookup"><span data-stu-id="62ddd-106">To prepare a domain to host servers running Skype for Business Server 2015 or Skype for Business Server users, you must complete **Step 5: Prepare Current Domain**, as described in the topic [Using Setup to Run Domain Preparation](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx).</span></span> <span data-ttu-id="62ddd-107">Per poter completare tale passaggio, è necessario essere connessi come membri del gruppo Domain Admins nel dominio che si sta preparando oppure come membri del gruppo Enterprise Admins della foresta a cui appartiene il dominio.</span><span class="sxs-lookup"><span data-stu-id="62ddd-107">To complete the step, you must be logged in as a member of the Domain Admins group in the domain that you are preparing, or as a member of the Enterprise Admins group of the forest that the domain belongs to.</span></span> <span data-ttu-id="62ddd-108">Per preparare il dominio, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="62ddd-108">To prepare the domain:</span></span>

1. <span data-ttu-id="62ddd-109">Dalla cartella o dal supporto di installazione di Skype for Business Server 2015, eseguire Setup.exe per avviare la Distribuzione guidata di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="62ddd-109">From the Skype for Business Server 2015 installation folder or media, run Setup.exe to start the Skype for Business Server Deployment Wizard.</span></span>

2. <span data-ttu-id="62ddd-110">Fare clic su **Prepara Active Directory** e quindi attendere che venga determinato lo stato della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="62ddd-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

3. <span data-ttu-id="62ddd-111">Al **Passaggio 5: Preparazione del dominio corrente**, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="62ddd-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

4. <span data-ttu-id="62ddd-112">Nella pagina **Esecuzione comandi in corso** ricercare **Stato attività: Operazione completata** e quindi fare clic su **Visualizza registro**.</span><span class="sxs-lookup"><span data-stu-id="62ddd-112">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

5. <span data-ttu-id="62ddd-113">Nella colonna **Azione** espandere **Preparazione** dominio, cercare un risultato di esecuzione alla fine di ogni attività per verificare che la preparazione del dominio sia stata completata correttamente, chiudere il registro e quindi fare clic **\<Success\>** su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="62ddd-113">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

> [!TIP]
> <span data-ttu-id="62ddd-114">Se è necessario esaminare i file di registro creati dalla Distribuzione guidata di Skype for Business Server, è possibile trovarli nel computer in cui è stata eseguita la Distribuzione guidata nella directory Utenti dell'utente di Servizi di dominio Active Directory che ha eseguito il passaggio.</span><span class="sxs-lookup"><span data-stu-id="62ddd-114">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="62ddd-115">Ad esempio, se l'utente ha eseguito l'accesso come amministratore di dominio nel Contoso.net di dominio, i file di registro si trovano in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span><span class="sxs-lookup"><span data-stu-id="62ddd-115">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp.</span></span>


