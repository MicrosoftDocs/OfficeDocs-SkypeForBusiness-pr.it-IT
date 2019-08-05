---
title: Selezionare regole di conversione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: Enterprise Voice richiede che tutte le stringhe di chiamata vengano normalizzate in formato E. 164 allo scopo di eseguire la ricerca di numeri inversa (RNL). Il peer trunk, ovvero il gateway, il centralino (PBX) o il trunk SIP associato, potrebbe richiedere che i numeri siano nel formato locale. Per convertire i numeri dal formato E.164 a un formato locale, è facoltativamente possibile definire una o più regole di conversione per gestire l'URI della richiesta prima di instradarlo al peer trunk. Ad esempio, è possibile scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.
ms.openlocfilehash: e6df4b2eed01849af7290596bc0e91896e527574
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191771"
---
# <a name="select-translation-rules"></a>Selezionare regole di conversione
 
 Enterprise Voice richiede che tutte le stringhe di chiamata vengano normalizzate in formato E. 164 allo scopo di eseguire la ricerca di numeri inversa (RNL). Il peer trunk, ovvero il gateway, il centralino (PBX) o il trunk SIP associato, potrebbe richiedere che i numeri siano nel formato locale. Per convertire i numeri dal formato E.164 a un formato locale, è facoltativamente possibile definire una o più regole di conversione per gestire l'URI della richiesta prima di instradarlo al peer trunk. Ad esempio, è possibile scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.
  
> [!IMPORTANT]
> La possibilità di associare una o più regole di traduzione a una configurazione trunk VoIP aziendale è destinata a essere usata come alternativa alla configurazione delle regole di traduzione nel trunk peer. Non associare regole di traduzione a una configurazione trunk VoIP aziendale se sono state configurate regole di traduzione nel peer trunk perché le due regole potrebbero essere in conflitto. 
  
Per utilizzare una regola di conversione esistente, selezionarla nell'elenco e quindi fare clic su **OK**.
  
 
  

