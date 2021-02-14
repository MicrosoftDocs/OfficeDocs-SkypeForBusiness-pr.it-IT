---
title: Aggiungere un server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per aggiungere un nuovo server a un pool di server esistente di uno dei tipi seguenti:'
ms.openlocfilehash: 853ed95ab456bcbbbeffec493effbe86d8894327
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811556"
---
# <a name="add-server"></a><span data-ttu-id="11dc1-103">Aggiungere server</span><span class="sxs-lookup"><span data-stu-id="11dc1-103">Add Server</span></span>
 
<span data-ttu-id="11dc1-104">Per aggiungere un nuovo server a un pool di server esistente di uno dei tipi seguenti:</span><span class="sxs-lookup"><span data-stu-id="11dc1-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="11dc1-105">Enterprise Edition Front End Server</span><span class="sxs-lookup"><span data-stu-id="11dc1-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="11dc1-106">Server Director</span><span class="sxs-lookup"><span data-stu-id="11dc1-106">Director server</span></span>
    
- <span data-ttu-id="11dc1-107">Mediation Server</span><span class="sxs-lookup"><span data-stu-id="11dc1-107">Mediation Server</span></span>
    
- <span data-ttu-id="11dc1-108">Audio/Video Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="11dc1-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="11dc1-109">Server applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="11dc1-109">Trusted Application server</span></span>
    
<span data-ttu-id="11dc1-p101">Ognuno dei nuovi server del pool ha requisiti diversi. Nelle sezioni riportate di seguito individuare il tipo di server che si intende aggiungere al pool esistente e specificare le informazioni richieste per il tipo di server in questione. È necessario fornire le informazioni richieste per definire il nuovo server del pool.</span><span class="sxs-lookup"><span data-stu-id="11dc1-p101">Each of the new pool servers has different requirements. In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type. You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="11dc1-113">**Enterprise Edition Front End Server**</span><span class="sxs-lookup"><span data-stu-id="11dc1-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="11dc1-114">Nome di dominio completo (FQDN) del nuovo server come definito in DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="11dc1-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="11dc1-p102">Selezionare **Usa tutti gli indirizzi IP configurati**, in modo che possa essere utilizzato qualsiasi indirizzo IP definito nel computer. In alternativa, è possibile selezionare **Limita utilizzo servizio a indirizzi IP selezionati** e immettere un indirizzo specifico per il nuovo server. L'indirizzo IP immesso sarà l'unico a rispondere per i servizi ospitati.</span><span class="sxs-lookup"><span data-stu-id="11dc1-p102">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="11dc1-118">Definire un **Indirizzo IP PSTN** quando un Mediation Server è collocato nel Front End Server.</span><span class="sxs-lookup"><span data-stu-id="11dc1-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="11dc1-119">Selezionare **Abilita IPv6** per abilitare IPv6 per questo server.</span><span class="sxs-lookup"><span data-stu-id="11dc1-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="11dc1-120">**Server Director**</span><span class="sxs-lookup"><span data-stu-id="11dc1-120">**Director server**</span></span>
  
- <span data-ttu-id="11dc1-121">FQDN del nuovo server come definito in DNS.</span><span class="sxs-lookup"><span data-stu-id="11dc1-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="11dc1-p103">Selezionare **Usa tutti gli indirizzi IP configurati**, in modo che possa essere usato qualsiasi indirizzo IP definito nel computer. In alternativa, selezionare **Limita utilizzo servizio a indirizzi IP selezionati** e immettere un indirizzo IP specifico per il nuovo server. L'indirizzo IP immesso sarà l'unico a rispondere per i servizi ospitati.</span><span class="sxs-lookup"><span data-stu-id="11dc1-p103">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="11dc1-125">**Mediation Server**</span><span class="sxs-lookup"><span data-stu-id="11dc1-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="11dc1-126">FQDN del nuovo server come definito in DNS.</span><span class="sxs-lookup"><span data-stu-id="11dc1-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="11dc1-p104">Selezionare **Usa tutti gli indirizzi IP configurati**, in modo che possa essere utilizzato qualsiasi indirizzo IP definito nel computer. In alternativa, selezionare **Limita utilizzo servizio a indirizzi IP selezionati** e immettere un indirizzo IP specifico per il nuovo server come indirizzo IP primario e immettere un indirizzo IP come indirizzo IP PSTN (Public Switched Telephone Network). Gli indirizzi IP immessi saranno gli unici a rispondere per i servizi designati.</span><span class="sxs-lookup"><span data-stu-id="11dc1-p104">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address. The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="11dc1-p105">Per il Mediation Server, l'indirizzo IP immesso come indirizzo IP primario e l'indirizzo IP PSTN sono uguali per impostazione predefinita. Gli indirizzi IP possono essere definiti separatamente se si usano interfacce di rete dedicate o indirizzi IP diversi nella stessa interfaccia di rete. Se si dispone di due interfacce di rete, una per la connessione di rete locale e l'altra per la connessione PSTN, sarà necessario assegnare indirizzi IP diversi.</span><span class="sxs-lookup"><span data-stu-id="11dc1-p105">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default. The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface. If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="11dc1-133">**Audio/Video Conferencing Server**</span><span class="sxs-lookup"><span data-stu-id="11dc1-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="11dc1-134">FQDN del nuovo server come definito in DNS.</span><span class="sxs-lookup"><span data-stu-id="11dc1-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="11dc1-p106">Selezionare **Usa tutti gli indirizzi IP configurati**, in modo che possa essere usato qualsiasi indirizzo IP definito nel computer. In alternativa, è possibile selezionare **Limita utilizzo servizio a indirizzi IP selezionati** e immettere un indirizzo specifico per il nuovo server. L'indirizzo IP immesso sarà l'unico a rispondere per i servizi ospitati.</span><span class="sxs-lookup"><span data-stu-id="11dc1-p106">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="11dc1-138">**Server applicazioni attendibili**</span><span class="sxs-lookup"><span data-stu-id="11dc1-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="11dc1-139">FQDN del nuovo server come definito in DNS.</span><span class="sxs-lookup"><span data-stu-id="11dc1-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

