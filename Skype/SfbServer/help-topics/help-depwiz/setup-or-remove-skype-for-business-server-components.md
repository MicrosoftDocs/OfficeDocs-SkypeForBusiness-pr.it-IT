---
title: Installare o rimuovere componenti di Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainBootstrap
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f8813f25-eafa-4006-a186-94e4ebcc5ac7
description: "Per installare e attivare o disattivare o disinstallare i componenti di Skype for Business Server 2015, è possibile utilizzare il passaggio 2: installazione o rimozione dei componenti del server Skype. È necessario aver eseguito l'accesso come amministratore locale nel computer in cui si sta installando o modificando e deve essere in grado di leggere gli utenti e i gruppi di servizi di dominio Active Directory nel dominio corrente. Per iniziare, fare clic su Esegui. In questo modo verrà letta la definizione della topologia basata sull'archivio di gestione centrale. I componenti software necessari vengono installati e configurati in base al ruolo secondo quanto definito nell'archivio di gestione centrale. Al termine dell'installazione, leggere il riepilogo e fare clic su Fine."
ms.openlocfilehash: 05144357e7346428c6c23f6482abd91a58e3779f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829626"
---
# <a name="setup-or-remove-skype-for-business-server-components"></a><span data-ttu-id="e6425-108">Installare o rimuovere componenti di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e6425-108">Setup or Remove Skype for Business Server Components</span></span>
 
<span data-ttu-id="e6425-109">Per installare e attivare o disattivare o disinstallare i componenti di Skype for Business Server 2015, è possibile utilizzare il **passaggio 2: installazione o rimozione dei componenti del server Skype**.</span><span class="sxs-lookup"><span data-stu-id="e6425-109">To install and activate, or deactivate or uninstall Skype for Business Server 2015 components, you use **Step 2: Setup or Remove Skype Server Components**.</span></span> <span data-ttu-id="e6425-110">È necessario aver eseguito l'accesso come amministratore locale nel computer in cui si sta installando o modificando e deve essere in grado di leggere gli utenti e i gruppi di servizi di dominio Active Directory nel dominio corrente.</span><span class="sxs-lookup"><span data-stu-id="e6425-110">You must be logged in as a local administrator on the computer that you are installing or modifying and must be able to read Active Directory Domain Services users and groups in the current domain.</span></span> <span data-ttu-id="e6425-111">Per iniziare, fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="e6425-111">To begin, click **Run**.</span></span> <span data-ttu-id="e6425-112">In questo modo verrà letta la definizione della topologia basata sull'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="e6425-112">When you do this, the Central Management store-based topology definition is read.</span></span> <span data-ttu-id="e6425-113">I componenti software necessari vengono installati e configurati in base al ruolo secondo quanto definito nell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="e6425-113">Necessary software components are installed and configured, according to the role as defined in the Central Management store.</span></span> <span data-ttu-id="e6425-114">Al termine dell'installazione, leggere il riepilogo e fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="e6425-114">When the installation is complete, review the Summary, and click **Finish**.</span></span>
  
> [!TIP]
> <span data-ttu-id="e6425-115">Se è necessario esaminare i file di registro creati tramite la distribuzione guidata, è possibile trovarli nel computer in cui è stata eseguita la distribuzione guidata, nella directory degli utenti dell'utente di Active Directory che ha eseguito il passaggio.</span><span class="sxs-lookup"><span data-stu-id="e6425-115">If you need to review the log files that are created by the Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="e6425-116">Ad esempio, se l'utente ha effettuato l'accesso come amministratore del dominio nel dominio Contoso.net, i file di registro sono disponibili in: > C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="e6425-116">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: > C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e6425-117">Se i componenti di Skype for Business Server 2015 sono stati precedentemente installati in questo computer, la distribuzione guidata lo riconoscerà e il pulsante nel passaggio 2 verrà visualizzato di **nuovo come Riesegui**.</span><span class="sxs-lookup"><span data-stu-id="e6425-117">If you have previously installed Skype for Business Server 2015 components on this computer, the Deployment Wizard will recognize this, and the button in step 2 will be displayed as **Run Again**.</span></span> <span data-ttu-id="e6425-118">Questo consente di eseguire il passaggio tutte le volte che è necessario per configurare correttamente o modificare il server.</span><span class="sxs-lookup"><span data-stu-id="e6425-118">This enables you to run the step as many times as needed to correctly configure or modify the server.</span></span> 
  

