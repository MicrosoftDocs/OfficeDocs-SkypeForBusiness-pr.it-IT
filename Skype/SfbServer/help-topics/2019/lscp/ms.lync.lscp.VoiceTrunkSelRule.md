---
title: Selezionare regole di conversione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: Enterprise Voice richiede che tutte le stringhe di chiamata vengano normalizzate in formato E. 164 allo scopo di eseguire la ricerca di numeri inversa (RNL). Il peer trunk, ovvero il gateway, il centralino (PBX) o il trunk SIP associato, potrebbe richiedere che i numeri siano nel formato locale. Per convertire i numeri dal formato E.164 a un formato locale, è facoltativamente possibile definire una o più regole di conversione per gestire l'URI della richiesta prima di instradarlo al peer trunk. Ad esempio, è possibile scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.
ms.openlocfilehash: d25e4641673db68332cc52d1771fa1655782eec1
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41690201"
---
# <a name="select-translation-rules"></a>Selezionare regole di conversione
 
 Enterprise Voice richiede che tutte le stringhe di chiamata vengano normalizzate in formato E. 164 allo scopo di eseguire la ricerca di numeri inversa (RNL). Il peer trunk, ovvero il gateway, il centralino (PBX) o il trunk SIP associato, potrebbe richiedere che i numeri siano nel formato locale. Per convertire i numeri dal formato E.164 a un formato locale, è facoltativamente possibile definire una o più regole di conversione per gestire l'URI della richiesta prima di instradarlo al peer trunk. Ad esempio, è possibile scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.
  
> [!IMPORTANT]
> La possibilità di associare una o più regole di traduzione a una configurazione trunk VoIP aziendale è destinata a essere usata come alternativa alla configurazione delle regole di traduzione nel trunk peer. Non associare regole di traduzione a una configurazione trunk VoIP aziendale se sono state configurate regole di traduzione nel peer trunk perché le due regole potrebbero essere in conflitto. 
  
Per utilizzare una regola di conversione esistente, selezionarla nell'elenco e quindi fare clic su **OK**.
  
 
  

