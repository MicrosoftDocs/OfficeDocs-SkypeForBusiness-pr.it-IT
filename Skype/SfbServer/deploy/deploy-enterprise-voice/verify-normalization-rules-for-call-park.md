---
title: Verificare le regole di normalizzazione per il parcheggio di chiamata in Skype for business
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
description: Informazioni sulle regole di normalizzazione per il parcheggio di chiamata in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: d1bcd6817b1f59f73a8c4ef1562e90253a99bd30
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830576"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Verificare le regole di normalizzazione per il parcheggio di chiamata in Skype for business
 
Informazioni sulle regole di normalizzazione per il parcheggio di chiamata in Skype for Business Server VoIP aziendale.
  
Le orbite del parcheggio di chiamata non devono essere normalizzate. Controllare i dial plan per assicurarsi che i numeri dell'orbita non siano normalizzati. Se è necessario creare una regola di normalizzazione aggiuntiva per evitare che le orbite vengano normalizzate, seguire la procedura descritta in [creare o modificare un dial plan in Skype for Business Server](dial-plans.md) per definire una nuova regola di normalizzazione, in modo che il **motivo corrispondente** identifichi l'intervallo di orbita e il **modello di conversione** sia **$1**. Ad esempio, se l'intervallo di orbit del parcheggio di chiamata è 7000-7999, il **motivo corrispondente** è **^ (7 \ d {3} ) $** e la modalità di **conversione** è **$1**.
  
> [!IMPORTANT]
> Verificare che la regola di normalizzazione predefinita nei dial plan non contenga **^ (\d \* )**. In caso contrario, la regola di normalizzazione del parcheggio di chiamata non verrà mai eseguita.
  
## <a name="see-also"></a>Vedere anche

[Creare o modificare un dial plan in Skype for Business Server](dial-plans.md)

