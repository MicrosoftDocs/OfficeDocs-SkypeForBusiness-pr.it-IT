---
title: Verificare le regole di normalizzazione per Call Park in Skype for business
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Informazioni sulle regole di normalizzazione per Call Park in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 769d9f9becccf4df24a33a11e8814350cfb091e8
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766889"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Verificare le regole di normalizzazione per Call Park in Skype for business
 
Informazioni sulle regole di normalizzazione per Call Park in Skype for Business Server VoIP aziendale.
  
Le orbite del parcheggio delle chiamate non devono essere normalizzate. Controlla i piani di chiamata per verificare che i numeri dell'orbita non siano normalizzati. Se è necessario creare una regola di normalizzazione aggiuntiva per evitare che le orbite vengano normalizzate, seguire la procedura descritta in [creare o modificare un dial plan in Skype for Business Server](dial-plans.md) per definire una nuova regola di normalizzazione, in modo che il **pattern da corrispondere** identifichi l'intervallo di orbite e il **modello di traduzione** sia **$1**. Ad esempio, se l'intervallo di Orbit di Call Park è 7000-7999, il **pattern da corrispondere** è **^ (7{3}\ d) $** e il **modello di traduzione** è **$1**.
  
> [!IMPORTANT]
> Assicurarsi che la regola di normalizzazione predefinita nei piani di chiamata non contenga **^ (\*\d)**. In caso contrario, la regola di normalizzazione del parcheggio delle chiamate non verrà mai eseguita.
  
## <a name="see-also"></a>Vedere anche

[Creare o modificare un dial plan in Skype for Business Server](dial-plans.md)

