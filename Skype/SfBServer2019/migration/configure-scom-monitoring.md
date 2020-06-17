---
title: Configurare il monitoraggio di SCOM
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dopo aver eseguito la migrazione a Microsoft Skype for Business Server 2019, è necessario completare alcune attività per configurare Skype for Business Server 2019 in modo che funzioni con System Center Operations Manager.
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754046"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="3a1ba-103">Configurare il monitoraggio di SCOM</span><span class="sxs-lookup"><span data-stu-id="3a1ba-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="3a1ba-104">Dopo aver eseguito la migrazione a Skype for Business Server 2019, è necessario completare alcune attività per configurare Skype for Business Server 2019 con System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="3a1ba-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="3a1ba-105">Applicare gli aggiornamenti a un server scelto per gestire la logica di individuazione centrale.</span><span class="sxs-lookup"><span data-stu-id="3a1ba-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="3a1ba-106">Aggiornare la chiave del Registro di sistema del server candidato all'individuazione centrale.</span><span class="sxs-lookup"><span data-stu-id="3a1ba-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="3a1ba-107">Configurare il server di gestione di System Center Operations Manager principale per eseguire l'override del nodo di individuazione centrale candidato.</span><span class="sxs-lookup"><span data-stu-id="3a1ba-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="3a1ba-108">Di seguito sono riportate le istruzioni per l'esecuzione di ognuna di tali attività.</span><span class="sxs-lookup"><span data-stu-id="3a1ba-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="3a1ba-109">Applicare gli aggiornamenti a un server scelto per gestire la logica di individuazione centrale.</span><span class="sxs-lookup"><span data-stu-id="3a1ba-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="3a1ba-110">Scegliere un server in cui siano installati i file dell'agente System Center Operations Manager e che sia configurato come nodo di individuazione candidato.</span><span class="sxs-lookup"><span data-stu-id="3a1ba-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="3a1ba-111">Applicare gli aggiornamenti a questo server.</span><span class="sxs-lookup"><span data-stu-id="3a1ba-111">Apply updates to this server.</span></span> <span data-ttu-id="3a1ba-112">Per ulteriori informazioni, vedere l'argomento [Apply Updates](apply-updates.md).</span><span class="sxs-lookup"><span data-stu-id="3a1ba-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="3a1ba-113">Aggiornare la chiave del Registro di sistema del server candidato all'individuazione centrale.</span><span class="sxs-lookup"><span data-stu-id="3a1ba-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="3a1ba-114">Nel server scelto per gestire la logica di individuazione centrale aprire una finestra di comando di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3a1ba-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="3a1ba-115">Digitare quanto segue alla riga di comando:</span><span class="sxs-lookup"><span data-stu-id="3a1ba-115">At the command line, type the following:</span></span>
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="3a1ba-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span><span class="sxs-lookup"><span data-stu-id="3a1ba-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="3a1ba-117">If you experience this, you can safely ignore the error.</span><span class="sxs-lookup"><span data-stu-id="3a1ba-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="3a1ba-118">Configurare il server di gestione di System Center Operations Manager principale per sostituire il nodo Watcher di individuazione centrale candidato.</span><span class="sxs-lookup"><span data-stu-id="3a1ba-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="3a1ba-119">In un computer in cui è stata installata la console System Center Operations Manager espandere **Oggetti Management Pack** e selezionare **Individuazioni oggetti**.</span><span class="sxs-lookup"><span data-stu-id="3a1ba-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="3a1ba-120">Fare clic su **Cambia ambito**</span><span class="sxs-lookup"><span data-stu-id="3a1ba-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="3a1ba-121">Nella pagina **Crea ambito oggetti Management Pack** selezionare **Candidato individuazione LS**.</span><span class="sxs-lookup"><span data-stu-id="3a1ba-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="3a1ba-122">Sostituire il **Valore effettivo candidato individuazione LS** con il nome del server candidato scelto nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="3a1ba-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="3a1ba-123">Per completare le modifiche, riavviare il servizio integrità nel server di gestione radice di System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="3a1ba-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

