---
title: Selezionare regole di conversione
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: VoIP aziendale richiede che tutte le stringhe di composizione vengano normalizzate nel formato E. 164 allo scopo di eseguire la ricerca di numeri inversi (inversa). Il peer trunk, ovvero il gateway, il centralino (PBX) o il trunk SIP associato, potrebbe richiedere che i numeri siano nel formato locale. Per convertire i numeri dal formato E.164 a un formato locale, è facoltativamente possibile definire una o più regole di conversione per gestire l'URI della richiesta prima di instradarlo al peer trunk. Ad esempio, è possibile scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.
ms.openlocfilehash: 033cfca7fcbb9cde12b585b7086dd7a8bf8d4de8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801316"
---
# <a name="select-translation-rules"></a>Selezionare regole di conversione
 
 VoIP aziendale richiede che tutte le stringhe di composizione vengano normalizzate nel formato E. 164 allo scopo di eseguire la ricerca di numeri inversi (inversa). Il peer trunk, ovvero il gateway, il centralino (PBX) o il trunk SIP associato, potrebbe richiedere che i numeri siano nel formato locale. Per convertire i numeri dal formato E.164 a un formato locale, è facoltativamente possibile definire una o più regole di conversione per gestire l'URI della richiesta prima di instradarlo al peer trunk. Ad esempio, è possibile scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.
  
> [!IMPORTANT]
> La possibilità di associare una o più regole di conversione a una configurazione trunk VoIP aziendale è destinata a essere utilizzata come alternativa alla configurazione delle regole di conversione nel peer trunk. Non associare regole di conversione a una configurazione trunk VoIP aziendale se sono state configurate regole di conversione nel peer trunk perché le due regole potrebbero essere in conflitto. 
  
Per utilizzare una regola di conversione esistente, selezionarla nell'elenco e quindi fare clic su **OK**.
  
 
  

