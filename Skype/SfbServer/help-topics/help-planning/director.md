---
title: Director (strumento di pianificazione)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Un Director è un server che esegue Skype for Business Server 2015 Communications software in grado di autenticare le richieste degli utenti, ma non gli account utente.
ms.openlocfilehash: 9809a6293c212a52dd87476069125540848ee2a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810546"
---
# <a name="director-planning-tool"></a><span data-ttu-id="8202f-103">Director (strumento di pianificazione)</span><span class="sxs-lookup"><span data-stu-id="8202f-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="8202f-104">Un Director è un server che esegue Skype for Business Server 2015 Communications software in grado di autenticare le richieste degli utenti, ma non gli account utente.</span><span class="sxs-lookup"><span data-stu-id="8202f-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="8202f-105">Questo ruolo è facoltativo, è possibile scegliere di distribuire un Director nei due scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="8202f-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="8202f-106">Se si Abilita l'accesso da parte di utenti esterni tramite la distribuzione di server perimetrali, è necessario distribuire anche un Director.</span><span class="sxs-lookup"><span data-stu-id="8202f-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="8202f-107">In questo scenario, il Director esegue l'autenticazione degli utenti esterni e quindi passa il traffico ai server interni.</span><span class="sxs-lookup"><span data-stu-id="8202f-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="8202f-108">Quando un amministratore viene utilizzato per autenticare gli utenti esterni, allevia i server del pool Front end dall'overhead dell'esecuzione dell'autenticazione di tali utenti.</span><span class="sxs-lookup"><span data-stu-id="8202f-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="8202f-109">Consente inoltre di isolare i pool Front end interni da traffico dannoso, ad esempio attacchi Denial of Service.</span><span class="sxs-lookup"><span data-stu-id="8202f-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="8202f-110">Se la rete è inondata da traffico esterno non valido durante un attacco di questo tipo, il traffico termina nel Director.</span><span class="sxs-lookup"><span data-stu-id="8202f-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="8202f-111">Se si distribuiscono più pool Front end in un sito centrale, aggiungendo un Director al sito è possibile semplificare le richieste di autenticazione e migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="8202f-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="8202f-112">In questo scenario, tutte le richieste passano prima al server Director, che le instrada al pool Front end corretto.</span><span class="sxs-lookup"><span data-stu-id="8202f-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

