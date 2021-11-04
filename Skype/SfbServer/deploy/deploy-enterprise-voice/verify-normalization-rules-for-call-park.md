---
title: Verificare le regole di normalizzazione per Parcheggio di chiamata in Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: ca76c15d7f71afa75e9b9247eab9cd96e5baedb0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771531"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Verificare le regole di normalizzazione per Parcheggio di chiamata in Skype for Business
 
Informazioni sulle regole di normalizzazione per Parcheggio di chiamata in Skype for Business Server VoIP aziendale.
  
I orbit del parcheggio di chiamata non devono essere normalizzati. Verificare che i dial plan non siano normalizzati. Se è necessario creare una regola di normalizzazione aggiuntiva per impedire la normalizzazione dei orbit, seguire la procedura descritta in Creare o modificare un [dial plan in Skype for Business Server per](dial-plans.md) definire una nuova regola di normalizzazione, in modo che Pattern to **match** identifichi l'intervallo di orbit e Il modello **di** conversione sia **$1**. Ad esempio, se l'intervallo di orbit del Parcheggio di chiamata è compreso tra 7000 e  7999, il **formato** da associare è **^(7\d {3} )$** e il modello di traduzione **è $1.**
  
> [!IMPORTANT]
> Assicurarsi che la regola di normalizzazione predefinita nei dial plan non contenga **^(\d \* ).** In caso contrario, la regola di normalizzazione del parcheggio di chiamata non verrà mai eseguita.
  
## <a name="see-also"></a>Vedere anche

[Creare o modificare un dial plan in Skype for Business Server](dial-plans.md)

