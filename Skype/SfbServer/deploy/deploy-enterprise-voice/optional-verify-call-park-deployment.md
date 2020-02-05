---
title: Opzionale Verificare la distribuzione di Call Park in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Verificare la distribuzione di Call Park in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 7dfaf916e94db18c3b53fc7e9c9e3b136fa445b8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767339"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="fbccf-103">Opzionale Verificare la distribuzione di Call Park in Skype for business</span><span class="sxs-lookup"><span data-stu-id="fbccf-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="fbccf-104">Verificare la distribuzione di Call Park in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="fbccf-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="fbccf-105">Dopo l'installazione e la configurazione di Call Park, è necessario verificare la configurazione per assicurarsi che il parcheggio e il recupero delle chiamate funzionino come previsto.</span><span class="sxs-lookup"><span data-stu-id="fbccf-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="fbccf-106">Verificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="fbccf-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="fbccf-107">Chiama un utente con il parcheggio delle chiamate abilitato e fai parcheggiare la chiamata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="fbccf-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fbccf-108">Se è stato abilitato Call Park in criteri vocali subito prima di eseguire questo test, l'utente che sta parcheggiando la chiamata deve disconnettersi da Skype for business e quindi eseguire di nuovo l'accesso per poter vedere l'opzione Call Park nell'elenco trasferimento chiamate.</span><span class="sxs-lookup"><span data-stu-id="fbccf-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="fbccf-109">Componi il numero dell'orbita per recuperare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fbccf-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="fbccf-110">Parcheggiare un'altra chiamata, consentire il timeout della chiamata parcheggiata e non ritirare la risponderia.</span><span class="sxs-lookup"><span data-stu-id="fbccf-110">Park another call, let the parked call time out, and do not pick up the ringback.</span></span> <span data-ttu-id="fbccf-111">Verificare che la chiamata scaduta venga indirizzata correttamente alla destinazione di fallback specificata per **OnTimeoutURI**.</span><span class="sxs-lookup"><span data-stu-id="fbccf-111">Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

