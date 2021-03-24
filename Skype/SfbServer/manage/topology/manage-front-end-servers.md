---
title: Gestire i Front End Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Riepilogo: informazioni su come aggiungere, rimuovere, applicare patch o aggiornare Front End Server in Skype for Business Server.'
ms.openlocfilehash: 24527a5f973b21c35e386f0565ac6deb69e15070
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103192"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="dc9b0-103">Gestire i Front End Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dc9b0-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="dc9b0-104">In questo articolo viene illustrato come aggiungere o rimuovere Front End Server e come applicare aggiornamenti o patch ai Front End Server.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

  > [!NOTE]
> <span data-ttu-id="dc9b0-105">Skype for Business Server 2019 non supporta pool Enterprise Edition Front End con due Front End Server e non consente la pubblicazione della topologia in tale scenario.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-105">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="dc9b0-106">Aggiungere o rimuovere Front End Server</span><span class="sxs-lookup"><span data-stu-id="dc9b0-106">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="dc9b0-107">Quando si aggiunge un Front End Server a un pool oppure si rimuove un Front End Server da un pool, è quindi necessario riavviare il pool.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-107">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="dc9b0-108">Quando si aggiunge o si rimuove un server al pool nella topologia e quindi si pubblica la topologia aggiornata, tutti i server del pool verranno riavviati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-108">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="dc9b0-109">Mentre i server stanno riavviando il pool è offline, il servizio verrà interrotto per gli utenti connessi a tale pool.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-109">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="dc9b0-110">Per evitare interruzioni del servizio per gli utenti, pianificare la pubblicazione della topologia con il nuovo server nel pool durante l'orario non di ufficio.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-110">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="dc9b0-111">È possibile utilizzare la procedura seguente quando si aggiunge o si rimuove un Front End Server.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-111">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc9b0-112">Se si aggiungono nuovi server al pool, aggiornare i nuovi server del pool in modo che siano allo stesso livello di aggiornamento cumulativo dei server esistenti nel pool.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-112">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="dc9b0-113">Per aggiungere o rimuovere Front End Server</span><span class="sxs-lookup"><span data-stu-id="dc9b0-113">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="dc9b0-p102">Se si desidera rimuovere uno o più Front End Server, innanzitutto interrompere le nuove connessioni a questi server. A tale scopo, è possibile utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="dc9b0-p102">If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="dc9b0-116">Aprire Generatore di topologie e aggiungere o rimuovere i server necessari.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-116">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="dc9b0-117">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-117">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="dc9b0-118">Quando si aggiunge o si rimuove un server al pool nella topologia e quindi si pubblica la topologia aggiornata, tutti i server del pool verranno riavviati contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-118">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="dc9b0-119">Mentre i server stanno riavviando il pool è offline, il servizio verrà interrotto per gli utenti connessi a tale pool.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-119">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="dc9b0-120">Per evitare interruzioni del servizio per gli utenti, pianificare la pubblicazione della topologia con il nuovo server nel pool durante l'orario non di ufficio.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-120">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="dc9b0-121">Inoltre, quando si aggiunge o si rimuove un server al pool, è necessario eseguire la Distribuzione guidata di Skype for Business Server in ogni computer aggiunto o rimosso, per ulteriori informazioni, vedere [Install Skype for Business Server on servers in the topology](../../deploy/install/install-skype-for-business-server.md)</span><span class="sxs-lookup"><span data-stu-id="dc9b0-121">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](../../deploy/install/install-skype-for-business-server.md)</span></span>
  
4. <span data-ttu-id="dc9b0-122">Se il numero di server nel pool Front End è stato modificato in uno dei modi seguenti, reimpostare il pool digitando il cmdlet seguente: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="dc9b0-122">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="dc9b0-123">2 a qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dc9b0-123">2 to any</span></span>
    
     - <span data-ttu-id="dc9b0-124">Da uno a 2</span><span class="sxs-lookup"><span data-stu-id="dc9b0-124">Any to 2</span></span>
    
     - <span data-ttu-id="dc9b0-125">3 a qualsiasi</span><span class="sxs-lookup"><span data-stu-id="dc9b0-125">3 to any</span></span>
    
     - <span data-ttu-id="dc9b0-126">Da uno a 3</span><span class="sxs-lookup"><span data-stu-id="dc9b0-126">Any to 3</span></span>
    
5. <span data-ttu-id="dc9b0-127">Riavviare il pool digitando il cmdlet seguente</span><span class="sxs-lookup"><span data-stu-id="dc9b0-127">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="dc9b0-128">Patch o aggiornamento dei Front End Server</span><span class="sxs-lookup"><span data-stu-id="dc9b0-128">Patch or update Front End Servers</span></span>

<span data-ttu-id="dc9b0-129">Quando si esegue la patch dei server in un pool Front End, si esegue questa operazione un server alla volta.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-129">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="dc9b0-130">Per applicare un aggiornamento ai Front End Server in un pool</span><span class="sxs-lookup"><span data-stu-id="dc9b0-130">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="dc9b0-131">Digitare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="dc9b0-131">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="dc9b0-132">Se questo cmdlet mostra eventuali repliche mancanti, eseguire il cmdlet seguente per ripristinare il pool prima di applicare eventuali patch.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-132">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="dc9b0-133">Nel primo server che si desidera applicare la patch, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="dc9b0-133">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="dc9b0-134">Questo cmdlet sposta tutti i servizi in altri Front End Server del pool e porta il server offline.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-134">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="dc9b0-135">Applicare l'aggiornamento o la patch a questo server.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-135">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="dc9b0-136">Nel server aggiornato eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="dc9b0-136">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="dc9b0-137">Il server viene restituito al servizio.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-137">The server is returned to service.</span></span>
    
5. <span data-ttu-id="dc9b0-138">Ripetere i passaggi da 2 a 4 per ogni server che deve essere aggiornato.</span><span class="sxs-lookup"><span data-stu-id="dc9b0-138">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
