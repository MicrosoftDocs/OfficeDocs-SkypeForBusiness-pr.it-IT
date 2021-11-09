---
title: (Facoltativo) Verificare la distribuzione del parcheggio di chiamata in Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Verifica della distribuzione del parcheggio di chiamata in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 9258a38936ffe22eb209c4b4bd9d1e5692341003
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838338"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(Facoltativo) Verificare la distribuzione del parcheggio di chiamata in Skype for Business
 
Verifica della distribuzione del parcheggio di chiamata in Skype for Business Server VoIP aziendale. 
  
Dopo aver installato e configurato Parcheggio di chiamata, è necessario verificare la configurazione per assicurarsi che il parcheggio e il recupero delle chiamate funzionino come previsto. Effettuare almeno le verifiche seguenti:
  
- Chiama un utente con Parcheggio di chiamata abilitato e che l'utente parcheggia la chiamata.
    
    > [!NOTE]
    > Se è stato abilitato Parcheggio di chiamata nei criteri vocali prima di eseguire questo test, l'utente che parcheggia la chiamata deve disconnettersi da Skype for Business e quindi accedere di nuovo per poter visualizzare l'opzione Parcheggio di chiamata nell'elenco chiamate di trasferimento. 
  
- Comporre il numero di orbit per recuperare la chiamata.
    
- Parcheggiare un'altra chiamata, attendere il timeout della chiamata parcheggiata e non rispondere alla richiamata. Verificare che dopo il timeout la chiamata venga correttamente instradata alla destinazione di fallback specificata per **OnTimeoutURI**.
    

