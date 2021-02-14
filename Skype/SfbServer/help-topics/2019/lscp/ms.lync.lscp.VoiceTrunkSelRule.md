---
title: Selezionare regole di conversione
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: VoIP aziendale che tutte le stringhe di composizione siano normalizzate nel formato E.164 allo scopo di eseguire la ricerca inversa dei numeri (RNL). Il peer trunk, ovvero il gateway, il centralino (PBX) o il trunk SIP associato, potrebbe richiedere che i numeri siano nel formato locale. Per convertire i numeri dal formato E.164 a un formato locale, è facoltativamente possibile definire una o più regole di conversione per gestire l'URI della richiesta prima di instradarlo al peer trunk. Ad esempio, è possibile scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.
ms.openlocfilehash: 033cfca7fcbb9cde12b585b7086dd7a8bf8d4de8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801316"
---
# <a name="select-translation-rules"></a><span data-ttu-id="a4976-106">Selezionare regole di conversione</span><span class="sxs-lookup"><span data-stu-id="a4976-106">Select Translation Rules</span></span>
 
 <span data-ttu-id="a4976-107">VoIP aziendale che tutte le stringhe di composizione siano normalizzate nel formato E.164 allo scopo di eseguire la ricerca inversa dei numeri (RNL).</span><span class="sxs-lookup"><span data-stu-id="a4976-107">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="a4976-108">Il peer trunk, ovvero il gateway, il centralino (PBX) o il trunk SIP associato, potrebbe richiedere che i numeri siano nel formato locale.</span><span class="sxs-lookup"><span data-stu-id="a4976-108">The trunk peer (that is, the associated gateway, PBX, or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="a4976-109">Per convertire i numeri dal formato E.164 a un formato locale, è facoltativamente possibile definire una o più regole di conversione per gestire l'URI della richiesta prima di instradarlo al peer trunk.</span><span class="sxs-lookup"><span data-stu-id="a4976-109">To translate numbers from E.164 format to a local dialing format, you can optionally define one or more translation rules to manipulate the Request URI before routing it to the trunk peer.</span></span> <span data-ttu-id="a4976-110">Ad esempio, è possibile scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.</span><span class="sxs-lookup"><span data-stu-id="a4976-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a4976-111">La possibilità di associare una o più regole di conversione a una configurazione di trunk VoIP aziendale deve essere utilizzata come alternativa alla configurazione delle regole di conversione nel trunk peer.</span><span class="sxs-lookup"><span data-stu-id="a4976-111">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="a4976-112">Non associare regole di conversione a una VoIP aziendale trunk se sono state configurate regole di conversione nel trunk peer perché le due regole potrebbero essere in conflitto.</span><span class="sxs-lookup"><span data-stu-id="a4976-112">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span> 
  
<span data-ttu-id="a4976-113">Per utilizzare una regola di conversione esistente, selezionarla nell'elenco e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4976-113">To use an existing translation rule, click a rule in the list and then click **OK**.</span></span>
  
 
  

