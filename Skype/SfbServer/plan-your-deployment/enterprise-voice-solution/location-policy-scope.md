---
title: Assegnare l'ambito dei criteri di posizione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Pianificazione dei criteri di posizione per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 3865db146676ed64da9422d2a8731e44451ec6ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802756"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="bb118-103">Assegnare l'ambito dei criteri di posizione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bb118-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="bb118-104">Pianificazione dei criteri di posizione per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="bb118-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="bb118-105">Come per altri criteri di Skype for Business Server, i criteri di posizione possono essere assegnati a più livelli di ambito: globale, sito e utente.</span><span class="sxs-lookup"><span data-stu-id="bb118-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="bb118-106">Tuttavia, l'ambito dei criteri di posizione a livello di utente si comporta in modo diverso rispetto a quello di altri criteri di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bb118-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="bb118-107">Non solo i criteri di posizione per utente possono essere applicati agli oggetti endpoint, ad esempio gli utenti e gli oggetti di contatto telefonico per l'area comune, ma possono essere applicati anche ai siti di rete di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="bb118-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="bb118-108">I siti di rete sono raggruppamenti di subnet client associati a una posizione geografica (ma potrebbero non essere necessariamente tutte le subnet di un intero sito centrale o di un sito di succursale).</span><span class="sxs-lookup"><span data-stu-id="bb118-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="bb118-109">Tutti i client connessi alle subnet in un sito di rete prelevano automaticamente i criteri di posizione assegnati al sito di rete.</span><span class="sxs-lookup"><span data-stu-id="bb118-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="bb118-110">Nei casi in cui un criterio di posizione a livello di utente viene assegnato sia a un utente che a un sito di rete, il criterio di posizione basato sul sito di rete sostituisce qualsiasi impostazione di criteri per utente.</span><span class="sxs-lookup"><span data-stu-id="bb118-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="bb118-111">A ogni sito di rete è assegnato un criterio di posizione e ogni criterio avrà diversi usi PSTN, URI di notifica e valori degli URI di conferenza assegnati.</span><span class="sxs-lookup"><span data-stu-id="bb118-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bb118-112">Il motivo di questo comportamento speciale per l'ambito dei criteri è che quando un utente ospitato in un pool di un sito di Office visita un altro sito e deve effettuare una chiamata di emergenza, le impostazioni di routing delle chiamate di E9-1-1 appropriate per il sito di rete verranno applicate indipendentemente dal pool o dal sito che si usa viene assegnato a ser.</span><span class="sxs-lookup"><span data-stu-id="bb118-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

