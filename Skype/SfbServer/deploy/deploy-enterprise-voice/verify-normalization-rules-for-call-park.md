---
title: Verificare le regole di normalizzazione per Parcheggio di chiamata in Skype for Business
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Informazioni sulle regole di normalizzazione per Parcheggio di chiamata in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 5c357a9ff9b2174ae414e1e4511cb7ebf267e19787091e19ce27f75f90b8a51e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298616"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Verificare le regole di normalizzazione per Parcheggio di chiamata in Skype for Business
 
Informazioni sulle regole di normalizzazione per Parcheggio di chiamata in Skype for Business Server VoIP aziendale.
  
I orbit del parcheggio di chiamata non devono essere normalizzati. Verificare che i dial plan non siano normalizzati. Se è necessario creare una regola di normalizzazione aggiuntiva per impedire la normalizzazione dei orbit, seguire la procedura descritta in Creare o modificare un [dial plan in Skype for Business Server per](dial-plans.md) definire una nuova regola di normalizzazione, in modo che Pattern to **match** identifichi l'intervallo di orbit e Il modello **di** conversione sia **$1**. Ad esempio, se l'intervallo di orbit del parcheggio di chiamata è 7000 - 7999, **il formato** da abbinare è **^(7\d {3} )$** e **il** modello di traduzione **è $1**.
  
> [!IMPORTANT]
> Assicurarsi che la regola di normalizzazione predefinita nei dial plan non contenga **^(\d \* ).** In caso contrario, la regola di normalizzazione del parcheggio di chiamata non verrà mai eseguita.
  
## <a name="see-also"></a>Vedere anche

[Creare o modificare un dial plan in Skype for Business Server](dial-plans.md)

