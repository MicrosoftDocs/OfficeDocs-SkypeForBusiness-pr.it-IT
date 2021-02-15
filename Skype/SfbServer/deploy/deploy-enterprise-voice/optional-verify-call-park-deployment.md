---
title: (Facoltativo) Verificare la distribuzione del parcheggio di chiamata in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Verifica della distribuzione del parcheggio di chiamata in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: a7edb9f47610bf7cdae068ca789670ab4048bb9c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830896"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="41910-103">(Facoltativo) Verificare la distribuzione del parcheggio di chiamata in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="41910-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="41910-104">Verifica della distribuzione del parcheggio di chiamata in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="41910-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="41910-105">Dopo aver installato e configurato il parcheggio di chiamata, è necessario verificare la configurazione per assicurarsi che il parcheggio e il recupero delle chiamate funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="41910-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="41910-106">Effettuare almeno le verifiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="41910-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="41910-107">Chiamare un utente che ha il parcheggio di chiamata abilitato e che l'utente parcheggia la chiamata.</span><span class="sxs-lookup"><span data-stu-id="41910-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="41910-108">Se il parcheggio di chiamata è stato abilitato nei criteri vocali appena prima di eseguire questo test, l'utente che parcheggia la chiamata deve disconnettersi da Skype for Business e quindi accedere di nuovo per poter visualizzare l'opzione Parcheggio di chiamata nell'elenco chiamate di trasferimento.</span><span class="sxs-lookup"><span data-stu-id="41910-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="41910-109">Comporre il numero di orbit per recuperare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="41910-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="41910-p102">Parcheggiare un'altra chiamata, attendere il timeout della chiamata parcheggiata e non rispondere alla richiamata. Verificare che dopo il timeout la chiamata venga correttamente instradata alla destinazione di fallback specificata per **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="41910-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

