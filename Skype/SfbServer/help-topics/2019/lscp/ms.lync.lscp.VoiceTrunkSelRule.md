---
title: Selezionare regole di conversione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: Enterprise Voice richiede che tutte le stringhe di chiamata vengano normalizzate in formato E. 164 allo scopo di eseguire la ricerca di numeri inversa (RNL). Il peer trunk, ovvero il gateway, il centralino (PBX) o il trunk SIP associato, potrebbe richiedere che i numeri siano nel formato locale. Per convertire i numeri dal formato E.164 a un formato locale, è facoltativamente possibile definire una o più regole di conversione per gestire l'URI della richiesta prima di instradarlo al peer trunk. Ad esempio, è possibile scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.
ms.openlocfilehash: e6df4b2eed01849af7290596bc0e91896e527574
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191771"
---
# <a name="select-translation-rules"></a><span data-ttu-id="6a026-106">Selezionare regole di conversione</span><span class="sxs-lookup"><span data-stu-id="6a026-106">Select Translation Rules</span></span>
 
 <span data-ttu-id="6a026-107">Enterprise Voice richiede che tutte le stringhe di chiamata vengano normalizzate in formato E. 164 allo scopo di eseguire la ricerca di numeri inversa (RNL).</span><span class="sxs-lookup"><span data-stu-id="6a026-107">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="6a026-108">Il peer trunk, ovvero il gateway, il centralino (PBX) o il trunk SIP associato, potrebbe richiedere che i numeri siano nel formato locale.</span><span class="sxs-lookup"><span data-stu-id="6a026-108">The trunk peer (that is, the associated gateway, PBX, or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="6a026-109">Per convertire i numeri dal formato E.164 a un formato locale, è facoltativamente possibile definire una o più regole di conversione per gestire l'URI della richiesta prima di instradarlo al peer trunk.</span><span class="sxs-lookup"><span data-stu-id="6a026-109">To translate numbers from E.164 format to a local dialing format, you can optionally define one or more translation rules to manipulate the Request URI before routing it to the trunk peer.</span></span> <span data-ttu-id="6a026-110">Ad esempio, è possibile scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.</span><span class="sxs-lookup"><span data-stu-id="6a026-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6a026-111">La possibilità di associare una o più regole di traduzione a una configurazione trunk VoIP aziendale è destinata a essere usata come alternativa alla configurazione delle regole di traduzione nel trunk peer.</span><span class="sxs-lookup"><span data-stu-id="6a026-111">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="6a026-112">Non associare regole di traduzione a una configurazione trunk VoIP aziendale se sono state configurate regole di traduzione nel peer trunk perché le due regole potrebbero essere in conflitto.</span><span class="sxs-lookup"><span data-stu-id="6a026-112">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span> 
  
<span data-ttu-id="6a026-113">Per utilizzare una regola di conversione esistente, selezionarla nell'elenco e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a026-113">To use an existing translation rule, click a rule in the list and then click **OK**.</span></span>
  
 
  

