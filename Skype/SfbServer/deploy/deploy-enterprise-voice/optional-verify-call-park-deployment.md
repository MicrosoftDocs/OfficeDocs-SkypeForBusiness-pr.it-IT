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
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>Opzionale Verificare la distribuzione di Call Park in Skype for business
 
Verificare la distribuzione di Call Park in Skype for Business Server VoIP aziendale. 
  
Dopo l'installazione e la configurazione di Call Park, è necessario verificare la configurazione per assicurarsi che il parcheggio e il recupero delle chiamate funzionino come previsto. Verificare quanto segue:
  
- Chiama un utente con il parcheggio delle chiamate abilitato e fai parcheggiare la chiamata dall'utente.
    
    > [!NOTE]
    > Se è stato abilitato Call Park in criteri vocali subito prima di eseguire questo test, l'utente che sta parcheggiando la chiamata deve disconnettersi da Skype for business e quindi eseguire di nuovo l'accesso per poter vedere l'opzione Call Park nell'elenco trasferimento chiamate. 
  
- Componi il numero dell'orbita per recuperare la chiamata.
    
- Parcheggiare un'altra chiamata, consentire il timeout della chiamata parcheggiata e non ritirare la risponderia. Verificare che la chiamata scaduta venga indirizzata correttamente alla destinazione di fallback specificata per **OnTimeoutURI**.
    

