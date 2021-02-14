---
title: Selezionare regole di conversione
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: VoIP aziendale che tutte le stringhe di composizione siano normalizzate nel formato E.164 allo scopo di eseguire la ricerca inversa dei numeri (RNL). Il peer trunk, ovvero il gateway, il centralino (PBX) o il trunk SIP associato, potrebbe richiedere che i numeri siano nel formato locale. Per convertire i numeri dal formato E.164 a un formato locale, è facoltativamente possibile definire una o più regole di conversione per gestire l'URI della richiesta prima di instradarlo al peer trunk. Ad esempio, è possibile scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.
ms.openlocfilehash: 3f448a9ac97c2bc7b57a8a87a6544ad84472e65e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803696"
---
# <a name="select-translation-rules"></a>Selezionare regole di conversione
 
 VoIP aziendale che tutte le stringhe di composizione siano normalizzate nel formato E.164 allo scopo di eseguire la ricerca inversa dei numeri (RNL). Il peer trunk, ovvero il gateway, il centralino (PBX) o il trunk SIP associato, potrebbe richiedere che i numeri siano nel formato locale. Per convertire i numeri dal formato E.164 a un formato locale, è facoltativamente possibile definire una o più regole di conversione per gestire l'URI della richiesta prima di instradarlo al peer trunk. Ad esempio, è possibile scrivere una regola di conversione per rimuovere +44 dall'inizio di una stringa di composizione e sostituirlo con 0144.
  
> [!IMPORTANT]
> La possibilità di associare una o più regole di conversione a una configurazione di trunk VoIP aziendale deve essere utilizzata come alternativa alla configurazione delle regole di conversione nel trunk peer. Non associare regole di conversione a una VoIP aziendale trunk se sono state configurate regole di conversione nel trunk peer perché le due regole potrebbero essere in conflitto. 
  
Per utilizzare una regola di conversione esistente, selezionarla nell'elenco e quindi fare clic su **OK**.
  
Per informazioni dettagliate sulle diverse procedure che è possibile eseguire utilizzando il Pannello di controllo di Skype for Business Server, vedere [Gestire Skype for Business Server 2015.](../../manage/manage.md)
  

