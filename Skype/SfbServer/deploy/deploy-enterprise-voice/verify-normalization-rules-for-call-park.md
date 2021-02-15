---
title: Verificare le regole di normalizzazione per il parcheggio di chiamata in Skype for Business
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
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>Verificare le regole di normalizzazione per il parcheggio di chiamata in Skype for Business
 
Informazioni sulle regole di normalizzazione per il parcheggio di chiamata in Skype for Business Server VoIP aziendale.
  
I orbit del parcheggio di chiamata non devono essere normalizzati. Controllare i dial plan per assicurarsi che i numeri orbit non siano normalizzati. Se è necessario creare una regola di normalizzazione aggiuntiva per evitare che i tuoi orbit vengano normalizzati, segui la procedura descritta in Creare o modificare un [dial plan in Skype for Business Server](dial-plans.md) per definire una nuova regola di normalizzazione, in modo che **pattern** corrispondente identifichi l'intervallo di orbit e **il** modello di conversione sia **$1.** Ad esempio, se l'intervallo di orbit del parcheggio di chiamata  è compreso tra 7000 e  7999, il formato da associare è **^(7\d {3} )$** e il modello di traduzione è **$1.**
  
> [!IMPORTANT]
> Assicurarsi che la regola di normalizzazione predefinita nei dial plan non contenga **^(\d \* ).** In caso contrario, la regola di normalizzazione del parcheggio di chiamata non verrà mai eseguita.
  
## <a name="see-also"></a>Vedere anche

[Creare o modificare un dial plan in Skype for Business Server](dial-plans.md)

