---
title: Configurare il monitoraggio di SCOM
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dopo aver eseguito la migrazione a Microsoft Skype for Business Server 2019, è necessario completare alcune attività per configurare Skype for Business Server 2019 per l'utilizzo con System Center Operations Manager.
ms.openlocfilehash: 141154a8bd678f15fcc919b2dd70a50ca9d4dcca
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190025"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="a90da-103">Configurare il monitoraggio di SCOM</span><span class="sxs-lookup"><span data-stu-id="a90da-103">Configure SCOM monitoring</span></span>

<span data-ttu-id="a90da-104">Dopo aver eseguito la migrazione a Skype for Business Server 2019, è necessario completare alcune attività per configurare Skype for Business Server 2019 per l'utilizzo con System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="a90da-104">After migrating to Skype for Business Server 2019, you must complete a few tasks to configure Skype for Business Server 2019 to work with System Center Operations Manager.</span></span>
  
- <span data-ttu-id="a90da-105">Applicare gli aggiornamenti a un server scelto per gestire la logica di individuazione centrale.</span><span class="sxs-lookup"><span data-stu-id="a90da-105">Apply updates to a server elected to manage the central discovery logic.</span></span>
    
- <span data-ttu-id="a90da-106">Aggiornare la chiave del registro di sistema del server di individuazione centrale.</span><span class="sxs-lookup"><span data-stu-id="a90da-106">Update the central discovery candidate server registry key.</span></span>
    
- <span data-ttu-id="a90da-107">Configurare il server di gestione di System Center Operations Manager principale per eseguire l'override del nodo di individuazione centrale candidata.</span><span class="sxs-lookup"><span data-stu-id="a90da-107">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>
    
<span data-ttu-id="a90da-108">Di seguito sono riportate le istruzioni per l'esecuzione di ciascuna di queste attività.</span><span class="sxs-lookup"><span data-stu-id="a90da-108">Instructions for carrying out each of these tasks are provided below.</span></span>
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a><span data-ttu-id="a90da-109">Applicare gli aggiornamenti a un server scelto per gestire la logica di individuazione centrale.</span><span class="sxs-lookup"><span data-stu-id="a90da-109">Apply updates to a server elected to manage the central discovery logic.</span></span>

1. <span data-ttu-id="a90da-110">Eleggere un server in cui sono installati i file dell'agente di System Center Operations Manager ed è configurato come nodo di individuazione candidata.</span><span class="sxs-lookup"><span data-stu-id="a90da-110">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span> 
    
2. <span data-ttu-id="a90da-111">Applicare gli aggiornamenti al server.</span><span class="sxs-lookup"><span data-stu-id="a90da-111">Apply updates to this server.</span></span> <span data-ttu-id="a90da-112">Vedere l'argomento [applicare gli aggiornamenti](apply-updates.md).</span><span class="sxs-lookup"><span data-stu-id="a90da-112">See the topic [Apply updates](apply-updates.md).</span></span>
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a><span data-ttu-id="a90da-113">Aggiornare la chiave del registro di sistema del server di individuazione centrale.</span><span class="sxs-lookup"><span data-stu-id="a90da-113">Update the central discovery candidate server registry key.</span></span>

1. <span data-ttu-id="a90da-114">Nel server scelto per gestire la logica di individuazione centrale aprire una finestra di comando di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a90da-114">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span> 
    
2. <span data-ttu-id="a90da-115">Nella riga di comando digitare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="a90da-115">At the command line, type the following:</span></span>
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > <span data-ttu-id="a90da-116">Ogni volta che si modifica il registro di sistema, potrebbe verificarsi un errore che indica che il comando non è riuscito se la chiave del registro di sistema esiste già.</span><span class="sxs-lookup"><span data-stu-id="a90da-116">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists.</span></span> <span data-ttu-id="a90da-117">Se si verifica questo problema, è possibile ignorare in modo sicuro l'errore.</span><span class="sxs-lookup"><span data-stu-id="a90da-117">If you experience this, you can safely ignore the error.</span></span> 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a><span data-ttu-id="a90da-118">Configurare il server di gestione di System Center Operations Manager principale per eseguire l'override del nodo di Watcher individuazione centrale candidato.</span><span class="sxs-lookup"><span data-stu-id="a90da-118">Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.</span></span>

1. <span data-ttu-id="a90da-119">In un computer in cui è installata la console di System Center Operations Manager, espandere **oggetti Management Pack** e quindi selezionare individuazioni **oggetti**.</span><span class="sxs-lookup"><span data-stu-id="a90da-119">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>
    
2. <span data-ttu-id="a90da-120">Fare clic su **Cambia ambito**</span><span class="sxs-lookup"><span data-stu-id="a90da-120">Click **Change Scope**</span></span>
    
3. <span data-ttu-id="a90da-121">Nella pagina **oggetti Management Pack di ambito** selezionare **ls Discovery candidate**.</span><span class="sxs-lookup"><span data-stu-id="a90da-121">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>
    
4. <span data-ttu-id="a90da-122">Eseguire l'override del **valore effettivo del candidato di individuazione LS** per il nome del server candidato eletto nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="a90da-122">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span> 
    
<span data-ttu-id="a90da-123">Per completare le modifiche, riavviare il servizio integrità nel server di gestione radice di System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="a90da-123">To finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>
  

