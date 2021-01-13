---
title: Assegnazione dell'ambito dei criteri percorso in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Pianificare i criteri percorso per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 586aabe919ea4236dc724446da717b5f300d88e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825526"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="44430-103">Assegnazione dell'ambito dei criteri percorso in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="44430-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="44430-104">Pianificare i criteri percorso per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="44430-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="44430-105">Come per gli altri criteri di Skype for Business Server, i criteri di percorso possono essere assegnati a più livelli di ambito: globale, sito e utente.</span><span class="sxs-lookup"><span data-stu-id="44430-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="44430-106">Tuttavia, l'ambito dei criteri percorso a livello di utente si comporta in modo diverso rispetto ad altri criteri di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="44430-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="44430-107">Non solo i criteri percorso per utente possono essere applicati agli oggetti endpoint (come gli utenti e gli oggetti contatto telefonici di area comune), che possono essere applicati anche ai siti di rete di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="44430-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="44430-108">I siti di rete sono raggruppamenti di subnet client associati a una posizione geografica (ma potrebbero non essere necessariamente tutte le subnet di un intero sito centrale o di un sito di succursale).</span><span class="sxs-lookup"><span data-stu-id="44430-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="44430-109">Tutti i client connessi alle subnet in un sito di rete raccolgono automaticamente il criterio percorso assegnato al sito di rete.</span><span class="sxs-lookup"><span data-stu-id="44430-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="44430-110">Nei casi in cui un criterio percorso a livello di utente sia assegnato a un utente e a un sito di rete, il criterio percorso basato sul sito di rete sostituisce qualsiasi impostazione di criteri per utente.</span><span class="sxs-lookup"><span data-stu-id="44430-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="44430-111">A ogni sito di rete è assegnato un criterio percorso e ogni criterio avrà diversi utilizzi PSTN, URI di notifica e valori URI di conferenza assegnati.</span><span class="sxs-lookup"><span data-stu-id="44430-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="44430-112">Il motivo di questo comportamento di ambito dei criteri speciali è tale che quando un utente ospitato in un pool di un sito di Office visita un altro sito e deve effettuare una chiamata di emergenza, le impostazioni di routing delle chiamate di E9-1-1 appropriate per il sito di rete verranno applicate indipendentemente dal pool o dal sito a cui l'utente è assegnato.</span><span class="sxs-lookup"><span data-stu-id="44430-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

