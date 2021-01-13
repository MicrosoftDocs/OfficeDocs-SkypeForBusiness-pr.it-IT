---
title: Aggiungere l'FQDN del pool di applicazioni attendibili
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per definire un nome di dominio completo (FQDN) per il pool di applicazioni attendibili, specificare quanto segue:'
ms.openlocfilehash: e34c3ba68a90e292da9441465d9077112b1ce173
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811816"
---
# <a name="add-trusted-application-pool-fqdn"></a><span data-ttu-id="90ff6-103">Aggiungere nome di dominio completo (FQDN) del pool di applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="90ff6-103">Add Trusted Application Pool FQDN</span></span>
 
<span data-ttu-id="90ff6-104">Per definire un nome di dominio completo (FQDN) per il pool di applicazioni attendibili, specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="90ff6-104">To define a Trusted Applications pool fully qualified domain name (FQDN), specify the following:</span></span>
  
<span data-ttu-id="90ff6-105">Un FQDN del server o del pool di server in cui saranno ospitate le applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="90ff6-105">An FQDN of the server or pool of servers that will host the trusted applications.</span></span>
  
<span data-ttu-id="90ff6-106">Selezionare **Pool di più computer** se si sta distribuendo un pool di server per le applicazioni attendibili per il bilanciamento del carico e la disponibilità elevata oppure selezionare **Pool computer singolo** se non si necessita del bilanciamento del carico o della disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="90ff6-106">Select **Multiple computer pool** if you are deploying a pool of servers for the trusted applications from load balancing and high availability, or select **Single computer pool** if you do not need load balancing or high availability.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="90ff6-p101">Un singolo server applicazioni attendibili non può essere convertito in un pool di server in un momento successivo. Se si ritiene di poter avere bisogno di un pool in futuro, è possibile distribuire subito un pool di più server contenente un solo computer e quindi aggiungere ulteriori server quando occorre.</span><span class="sxs-lookup"><span data-stu-id="90ff6-p101">A single Trusted Applications Server cannot be converted to a pool of servers later. If you think you may need a pool in the future, you can deploy a multiple server pool containing a single computer now, and add servers when needed.</span></span> 
  
<span data-ttu-id="90ff6-109">Per informazioni dettagliate sui pool di applicazioni attendibili, vedere [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="90ff6-109">For details about Trusted Applications pools, see [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps).</span></span>
  

