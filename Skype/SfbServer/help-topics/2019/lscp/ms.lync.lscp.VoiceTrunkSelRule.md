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
ms.localizationpriority: medium
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: VoIP aziendale che tutte le stringhe di composizione siano normalizzate nel formato E.164 allo scopo di eseguire la ricerca di numeri inversa (RNL). Il peer trunk, ovvero il gateway, il centralino (PBX) o il trunk SIP associato, potrebbe richiedere che i numeri siano nel formato locale. Per convertire i numeri dal formato E.164 a un formato locale, è facoltativamente possibile definire una o più regole di conversione per gestire l'URI della richiesta prima di instradarlo al peer trunk. Ad esempio, è possibile scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.
ms.openlocfilehash: fa41f3f67289f5929c34e410191e69e7fc25c2d4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58607195"
---
# <a name="select-translation-rules"></a>Selezionare regole di conversione
 
 VoIP aziendale che tutte le stringhe di composizione siano normalizzate nel formato E.164 allo scopo di eseguire la ricerca di numeri inversa (RNL). Il peer trunk, ovvero il gateway, il centralino (PBX) o il trunk SIP associato, potrebbe richiedere che i numeri siano nel formato locale. Per convertire i numeri dal formato E.164 a un formato locale, è facoltativamente possibile definire una o più regole di conversione per gestire l'URI della richiesta prima di instradarlo al peer trunk. Ad esempio, è possibile scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.
  
> [!IMPORTANT]
> La possibilità di associare una o più regole di conversione a una configurazione trunk VoIP aziendale è progettata per essere utilizzata come alternativa alla configurazione delle regole di conversione nel trunk peer. Non associare regole di conversione a una VoIP aziendale trunk se sono state configurate regole di conversione nel trunk peer perché le due regole potrebbero essere in conflitto. 
  
Per utilizzare una regola di conversione esistente, selezionarla nell'elenco e quindi fare clic su **OK**.
  
 
  

