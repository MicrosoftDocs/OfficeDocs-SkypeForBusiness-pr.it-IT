---
title: Director (strumento di pianificazione)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
ROBOTS: NOINDEX, NOFOLLOW
description: Un amministratore è un server che esegue Skype for Business Server Communications software che può autenticare le richieste degli utenti, ma non ospita gli account utente.
ms.openlocfilehash: 529c9c0feea8d5ed3e28ee132f64c73228c6bd60
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689861"
---
# <a name="director-planning-tool"></a><span data-ttu-id="a01b4-103">Director (strumento di pianificazione)</span><span class="sxs-lookup"><span data-stu-id="a01b4-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="a01b4-104">Un amministratore è un server che esegue Skype for Business Server Communications software che può autenticare le richieste degli utenti, ma non ospita gli account utente.</span><span class="sxs-lookup"><span data-stu-id="a01b4-104">A Director is a server running Skype for Business Server communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="a01b4-105">Questo ruolo è facoltativo, si sceglie di distribuire un Director nei due scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="a01b4-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="a01b4-106">Se si Abilita l'accesso da parte di utenti esterni distribuendo Edge Server, è anche necessario distribuire un Director.</span><span class="sxs-lookup"><span data-stu-id="a01b4-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="a01b4-107">In questo scenario, il Director esegue l'autenticazione degli utenti esterni e quindi passa il traffico ai server interni.</span><span class="sxs-lookup"><span data-stu-id="a01b4-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="a01b4-108">Quando un amministratore viene usato per autenticare utenti esterni, allevia i server del pool Front-end dall'overhead dell'esecuzione dell'autenticazione di questi utenti.</span><span class="sxs-lookup"><span data-stu-id="a01b4-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="a01b4-109">Consente inoltre di isolare i pool di front-end interni da traffico illecito, ad esempio attacchi Denial of Service.</span><span class="sxs-lookup"><span data-stu-id="a01b4-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="a01b4-110">Se la rete viene allagata con traffico esterno non valido in un attacco di questo tipo, il traffico termina con il direttore.</span><span class="sxs-lookup"><span data-stu-id="a01b4-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="a01b4-111">Se si distribuiscono più pool Front-end in un sito centrale, aggiungendo un Director al sito è possibile semplificare le richieste di autenticazione e migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="a01b4-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="a01b4-112">In questo scenario tutte le richieste vanno prima di tutto al Director, che li instrada al pool Front end corretto.</span><span class="sxs-lookup"><span data-stu-id="a01b4-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

