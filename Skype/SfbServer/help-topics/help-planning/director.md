---
title: Director (strumento di pianificazione)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Un Director è un server che esegue il software di comunicazione Skype for Business Server 2015 che può autenticare le richieste degli utenti, ma non ospita alcun account utente.
ms.openlocfilehash: 9809a6293c212a52dd87476069125540848ee2a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810546"
---
# <a name="director-planning-tool"></a>Director (strumento di pianificazione)
 
Un Director è un server che esegue il software di comunicazione Skype for Business Server 2015 che può autenticare le richieste degli utenti, ma non ospita alcun account utente. 
  
Questo ruolo è facoltativo, è possibile scegliere di distribuire un Director nei due scenari seguenti:
  
- Se si abilita l'accesso da parte di utenti esterni distribuendo server perimetrali, è necessario distribuire anche un Director. In questo scenario, il Director autentica gli utenti esterni e quindi passa il traffico ai server interni. Quando si utilizza un Director per autenticare gli utenti esterni, i server del pool Front End non possono essere utilizzati per l'autenticazione di tali utenti. Consente inoltre di isolare i pool Front End interni da traffico dannoso, ad esempio attacchi Denial of Service. Se la rete è inondata da traffico esterno non valido durante un attacco di questo tipo, il traffico termina nel Director.
    
- Se si distribuiscono più pool Front End in un sito centrale, aggiungendo un Director a tale sito è possibile semplificare le richieste di autenticazione e migliorare le prestazioni. In questo scenario, tutte le richieste passano prima al Director, che quindi le instrada al pool Front End corretto.
    

