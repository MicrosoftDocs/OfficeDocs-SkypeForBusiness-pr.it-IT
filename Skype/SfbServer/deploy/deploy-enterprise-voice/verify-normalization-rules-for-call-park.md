---
title: Verificare le regole di normalizzazione per Call Park in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: Informazioni sulle regole di normalizzazione per Call Park in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 36e9a91ff1269caffb8eab5be9a2c681d3244b31
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195207"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Verificare le regole di normalizzazione per Call Park in Skype for business
 
Informazioni sulle regole di normalizzazione per Call Park in Skype for Business Server VoIP aziendale.
  
Le orbite del parcheggio delle chiamate non devono essere normalizzate. Controlla i piani di chiamata per verificare che i numeri dell'orbita non siano normalizzati. Se è necessario creare una regola di normalizzazione aggiuntiva per evitare che le orbite vengano normalizzate, seguire la procedura descritta in [creare o modificare un dial plan in Skype for Business Server](dial-plans.md) per definire una nuova regola di normalizzazione, in modo che il **modello corrisponda** identifica l'intervallo di orbite e il **modello di traduzione** è **$1**. Ad esempio, se l'intervallo di Orbit di Call Park è 7000-7999, il **pattern da corrispondere** è **^ (7{3}\ d) $** e il **modello di traduzione** è **$1**.
  
> [!IMPORTANT]
> Assicurarsi che la regola di normalizzazione predefinita nei piani di chiamata non contenga **^ (\*\d)**. In caso contrario, la regola di normalizzazione del parcheggio delle chiamate non verrà mai eseguita.
  
## <a name="see-also"></a>Vedere anche

[Creare o modificare un dial plan in Skype for Business Server](dial-plans.md)

