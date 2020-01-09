---
title: Gestire i server front-end in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 'Riepilogo: informazioni su come aggiungere, rimuovere, patch o aggiornare i server front-end in Skype for Business Server.'
ms.openlocfilehash: 3689b869ba715f431ebcf0b537b4106a66177c62
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991531"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="931bd-103">Gestire i server front-end in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="931bd-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="931bd-104">Questo articolo illustra come aggiungere o rimuovere front-end server e come applicare gli aggiornamenti o le patch ai server front-end.</span><span class="sxs-lookup"><span data-stu-id="931bd-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="931bd-105">Aggiungere o rimuovere server front-end</span><span class="sxs-lookup"><span data-stu-id="931bd-105">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="931bd-106">Quando si aggiunge un server front-end a un pool o si rimuove un server front-end da un pool, è necessario riavviare il pool.</span><span class="sxs-lookup"><span data-stu-id="931bd-106">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="931bd-107">Quando si aggiunge o si rimuove un server nel pool della topologia e quindi si pubblica la topologia aggiornata, tutti i server del pool verranno riavviati simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="931bd-107">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="931bd-108">Mentre i server riavviano il pool è offline, il servizio verrà interrotto per gli utenti connessi al pool.</span><span class="sxs-lookup"><span data-stu-id="931bd-108">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="931bd-109">Per impedire l'interruzione del servizio agli utenti, pianificare la pubblicazione della topologia con il nuovo server nel pool durante le ore non lavorative.</span><span class="sxs-lookup"><span data-stu-id="931bd-109">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="931bd-110">Quando si aggiunge o si rimuove un server front-end, è possibile usare la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="931bd-110">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="931bd-111">Se si aggiungono nuovi server al pool, aggiornare i nuovi server del pool in modo che si trovino nello stesso livello di aggiornamento cumulativo dei server esistenti nel pool.</span><span class="sxs-lookup"><span data-stu-id="931bd-111">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="931bd-112">Per aggiungere o rimuovere i server front-end</span><span class="sxs-lookup"><span data-stu-id="931bd-112">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="931bd-113">Se si stanno rimuovendo i server front-end, arrestare prima le nuove connessioni a tali server.</span><span class="sxs-lookup"><span data-stu-id="931bd-113">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="931bd-114">A questo scopo, puoi usare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="931bd-114">To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="931bd-115">Aprire Generatore di topologia e aggiungere o rimuovere i server necessari.</span><span class="sxs-lookup"><span data-stu-id="931bd-115">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="931bd-116">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="931bd-116">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="931bd-117">Quando si aggiunge o si rimuove un server nel pool della topologia e quindi si pubblica la topologia aggiornata, tutti i server del pool verranno riavviati simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="931bd-117">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="931bd-118">Mentre i server riavviano il pool è offline, il servizio verrà interrotto per gli utenti connessi al pool.</span><span class="sxs-lookup"><span data-stu-id="931bd-118">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="931bd-119">Per impedire l'interruzione del servizio agli utenti, pianificare la pubblicazione della topologia con il nuovo server nel pool durante le ore non lavorative.</span><span class="sxs-lookup"><span data-stu-id="931bd-119">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="931bd-120">Inoltre, quando si aggiunge o si rimuove un server nel pool, è necessario eseguire la distribuzione guidata di Skype for Business Server su ogni computer aggiunto o rimosso, per altre informazioni, vedere [installare Skype for Business Server nei server della topologia](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="931bd-120">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="931bd-121">Se il numero di server nel pool Front-End è stato modificato in uno dei modi seguenti, reimpostare il pool con il cmdlet seguente: Reset-CsPoolRegistrarState-ResetType FullReset-PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="931bd-121">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="931bd-122">2 a qualsiasi</span><span class="sxs-lookup"><span data-stu-id="931bd-122">2 to any</span></span>
    
     - <span data-ttu-id="931bd-123">Qualsiasi a 2</span><span class="sxs-lookup"><span data-stu-id="931bd-123">Any to 2</span></span>
    
     - <span data-ttu-id="931bd-124">3 a qualsiasi</span><span class="sxs-lookup"><span data-stu-id="931bd-124">3 to any</span></span>
    
     - <span data-ttu-id="931bd-125">Qualsiasi a 3</span><span class="sxs-lookup"><span data-stu-id="931bd-125">Any to 3</span></span>
    
5. <span data-ttu-id="931bd-126">Riavviare il pool digitando il cmdlet seguente</span><span class="sxs-lookup"><span data-stu-id="931bd-126">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="931bd-127">Patch o aggiornamento dei Front End Server</span><span class="sxs-lookup"><span data-stu-id="931bd-127">Patch or update Front End Servers</span></span>

<span data-ttu-id="931bd-128">Quando si esegue la patch dei server in un pool Front-End, è possibile farlo un server alla volta.</span><span class="sxs-lookup"><span data-stu-id="931bd-128">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="931bd-129">Per applicare un aggiornamento ai server front-end in un pool</span><span class="sxs-lookup"><span data-stu-id="931bd-129">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="931bd-130">Digitare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="931bd-130">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="931bd-131">Se questo cmdlet Mostra le eventuali repliche mancanti, eseguire il cmdlet seguente per recuperare il pool prima di applicare eventuali patch.</span><span class="sxs-lookup"><span data-stu-id="931bd-131">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="931bd-132">Nel primo server che si vuole applicare, eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="931bd-132">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="931bd-133">Questo cmdlet sposta tutti i servizi in altri server front-end nel pool e non è in linea con questo server.</span><span class="sxs-lookup"><span data-stu-id="931bd-133">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="931bd-134">Applicare l'aggiornamento o la patch al server.</span><span class="sxs-lookup"><span data-stu-id="931bd-134">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="931bd-135">Nel server aggiornato eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="931bd-135">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="931bd-136">Il server viene restituito al servizio.</span><span class="sxs-lookup"><span data-stu-id="931bd-136">The server is returned to service.</span></span>
    
5. <span data-ttu-id="931bd-137">Ripetere i passaggi 2-4 per ogni server che deve essere aggiornato.</span><span class="sxs-lookup"><span data-stu-id="931bd-137">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
