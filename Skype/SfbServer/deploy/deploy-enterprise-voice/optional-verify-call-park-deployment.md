---
title: Opzionale Verificare la distribuzione di Call Park in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Verificare la distribuzione di Call Park in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 94d230491c0207c05016545de3c45cf0582ca496
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194343"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>Opzionale Verificare la distribuzione di Call Park in Skype for business
 
Verificare la distribuzione di Call Park in Skype for Business Server VoIP aziendale. 
  
Dopo l'installazione e la configurazione di Call Park, è necessario verificare la configurazione per assicurarsi che il parcheggio e il recupero delle chiamate funzionino come previsto. Verificare quanto segue:
  
- Chiama un utente con il parcheggio delle chiamate abilitato e fai parcheggiare la chiamata dall'utente.
    
    > [!NOTE]
    > Se è stato abilitato Call Park in criteri vocali subito prima di eseguire questo test, l'utente che sta parcheggiando la chiamata deve disconnettersi da Skype for business e quindi eseguire di nuovo l'accesso per poter vedere l'opzione Call Park nell'elenco trasferimento chiamate. 
  
- Componi il numero dell'orbita per recuperare la chiamata.
    
- Parcheggiare un'altra chiamata, consentire il timeout della chiamata parcheggiata e non ritirare la risponderia. Verificare che la chiamata scaduta venga indirizzata correttamente alla destinazione di fallback specificata per **OnTimeoutURI**.
    

