---
title: Aggiungere un server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per aggiungere un nuovo server a un pool di server esistente, in cui il pool è uno dei seguenti:'
ms.openlocfilehash: 005c2e2e63668b7c17ee04d49de88811649fe914
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194977"
---
# <a name="add-server"></a><span data-ttu-id="58ca4-103">Aggiungere un server</span><span class="sxs-lookup"><span data-stu-id="58ca4-103">Add Server</span></span>
 
<span data-ttu-id="58ca4-104">Per aggiungere un nuovo server a un pool di server esistente, in cui il pool è uno dei seguenti:</span><span class="sxs-lookup"><span data-stu-id="58ca4-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="58ca4-105">Server front-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="58ca4-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="58ca4-106">Server Director</span><span class="sxs-lookup"><span data-stu-id="58ca4-106">Director server</span></span>
    
- <span data-ttu-id="58ca4-107">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="58ca4-107">Mediation Server</span></span>
    
- <span data-ttu-id="58ca4-108">Server di conferenza audio/video</span><span class="sxs-lookup"><span data-stu-id="58ca4-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="58ca4-109">Server applicazioni attendibile</span><span class="sxs-lookup"><span data-stu-id="58ca4-109">Trusted Application server</span></span>
    
<span data-ttu-id="58ca4-110">Ogni nuovo server del pool ha requisiti diversi.</span><span class="sxs-lookup"><span data-stu-id="58ca4-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="58ca4-111">Nelle sezioni seguenti individuare il tipo di server che si sta aggiungendo al pool esistente e fornire le informazioni richieste come definito per ogni tipo di server.</span><span class="sxs-lookup"><span data-stu-id="58ca4-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="58ca4-112">Fornisci le informazioni richieste per definire il nuovo server del pool.</span><span class="sxs-lookup"><span data-stu-id="58ca4-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="58ca4-113">**Server front-end Enterprise Edition**</span><span class="sxs-lookup"><span data-stu-id="58ca4-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="58ca4-114">Nome di dominio completo (FQDN) del nuovo server come definito in Domain Name System (DNS).</span><span class="sxs-lookup"><span data-stu-id="58ca4-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="58ca4-115">Selezionare **Usa tutti gli indirizzi IP**configurati, il che significa che è possibile usare qualsiasi indirizzo IP definito nel computer.</span><span class="sxs-lookup"><span data-stu-id="58ca4-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="58ca4-116">In alternativa, è possibile selezionare **limita l'utilizzo del servizio agli indirizzi IP selezionati** e immettere un indirizzo specifico nel nuovo server.</span><span class="sxs-lookup"><span data-stu-id="58ca4-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="58ca4-117">L'indirizzo IP immesso è l'unico indirizzo IP che risponderà per i servizi ospitati.</span><span class="sxs-lookup"><span data-stu-id="58ca4-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="58ca4-118">Definire un **indirizzo IP PSTN** quando un Mediation Server è collocato nel server front-end.</span><span class="sxs-lookup"><span data-stu-id="58ca4-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="58ca4-119">Selezionare **Abilita IPv6** per abilitare IPv6 per il server.</span><span class="sxs-lookup"><span data-stu-id="58ca4-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="58ca4-120">**Server Director**</span><span class="sxs-lookup"><span data-stu-id="58ca4-120">**Director server**</span></span>
  
- <span data-ttu-id="58ca4-121">Il nome di dominio completo del nuovo server come definito in DNS.</span><span class="sxs-lookup"><span data-stu-id="58ca4-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="58ca4-122">Selezionare **Usa tutti gli indirizzi IP**configurati, il che significa che verrà usato qualsiasi indirizzo IP definito nel computer.</span><span class="sxs-lookup"><span data-stu-id="58ca4-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="58ca4-123">In alternativa, selezionare **limita l'utilizzo del servizio agli indirizzi IP selezionati** e immettere un indirizzo IP specifico nel nuovo server.</span><span class="sxs-lookup"><span data-stu-id="58ca4-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="58ca4-124">L'indirizzo IP immesso è l'unico indirizzo IP che risponderà per i servizi ospitati.</span><span class="sxs-lookup"><span data-stu-id="58ca4-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="58ca4-125">**Mediation Server**</span><span class="sxs-lookup"><span data-stu-id="58ca4-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="58ca4-126">Il nome di dominio completo del nuovo server come definito in DNS.</span><span class="sxs-lookup"><span data-stu-id="58ca4-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="58ca4-127">Selezionare **Usa tutti gli indirizzi IP**configurati, il che significa che è possibile usare qualsiasi indirizzo IP definito nel computer.</span><span class="sxs-lookup"><span data-stu-id="58ca4-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="58ca4-128">In alternativa, selezionare **limita l'utilizzo del servizio agli indirizzi IP selezionati** e immettere un indirizzo IP specifico nel nuovo server come indirizzo IP principale e immettere un indirizzo IP per l'indirizzo IP PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="58ca4-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="58ca4-129">Gli indirizzi IP immessi sono l'unico indirizzo IP che risponderà per i servizi designati.</span><span class="sxs-lookup"><span data-stu-id="58ca4-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="58ca4-130">Per il Mediation Server, l'indirizzo IP immesso per l'indirizzo IP principale e l'indirizzo IP PSTN è lo stesso per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="58ca4-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="58ca4-131">Gli indirizzi IP possono essere definiti separatamente se si usano interfacce di rete dedicate o indirizzi IP separati nella stessa interfaccia di rete.</span><span class="sxs-lookup"><span data-stu-id="58ca4-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="58ca4-132">Se si dispone di due interfacce di rete, una per la connessione di rete locale e una per la connessione PSTN, è necessario assegnare indirizzi IP diversi.</span><span class="sxs-lookup"><span data-stu-id="58ca4-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="58ca4-133">**Server di conferenza audio/video**</span><span class="sxs-lookup"><span data-stu-id="58ca4-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="58ca4-134">Il nome di dominio completo del nuovo server come definito in DNS.</span><span class="sxs-lookup"><span data-stu-id="58ca4-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="58ca4-135">Selezionare **Usa tutti gli indirizzi IP**configurati, il che significa che è possibile usare qualsiasi indirizzo IP definito nel computer.</span><span class="sxs-lookup"><span data-stu-id="58ca4-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="58ca4-136">In alternativa, è possibile selezionare **limita l'utilizzo del servizio agli indirizzi IP selezionati** e immettere un indirizzo specifico nel nuovo server.</span><span class="sxs-lookup"><span data-stu-id="58ca4-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="58ca4-137">L'indirizzo IP immesso è l'unico indirizzo IP che risponderà per i servizi ospitati.</span><span class="sxs-lookup"><span data-stu-id="58ca4-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="58ca4-138">**Server applicazioni attendibile**</span><span class="sxs-lookup"><span data-stu-id="58ca4-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="58ca4-139">Il nome di dominio completo del nuovo server come definito in DNS.</span><span class="sxs-lookup"><span data-stu-id="58ca4-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

