---
title: Verificare le regole di normalizzazione per Parcheggio di chiamata in Skype for Business
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Informazioni sulle regole di normalizzazione per Parcheggio di chiamata in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 2928044f5b10d579ed9e7ffa44acdb3248b32008
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835864"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Verificare le regole di normalizzazione per Parcheggio di chiamata in Skype for Business
 
Informazioni sulle regole di normalizzazione per Parcheggio di chiamata in Skype for Business Server VoIP aziendale.
  
I orbit del parcheggio di chiamata non devono essere normalizzati. Verificare che i dial plan non siano normalizzati. Se è necessario creare una regola di normalizzazione aggiuntiva per impedire la normalizzazione dei orbit, seguire la procedura descritta in Creare o modificare un [dial plan in Skype for Business Server per](dial-plans.md) definire una nuova regola di normalizzazione, in modo che Pattern to **match** identifichi l'intervallo di orbit e Il modello **di** conversione sia **$1**. Ad esempio, se l'intervallo di orbit del Parcheggio di chiamata è compreso tra 7000 e  7999, il **formato** da associare è **^(7\d {3} )$** e il modello di traduzione **è $1.**
  
> [!IMPORTANT]
> Assicurarsi che la regola di normalizzazione predefinita nei dial plan non contenga **^(\d \* ).** In caso contrario, la regola di normalizzazione del parcheggio di chiamata non verrà mai eseguita.
  
## <a name="see-also"></a>Vedere anche

[Creare o modificare un dial plan in Skype for Business Server](dial-plans.md)

