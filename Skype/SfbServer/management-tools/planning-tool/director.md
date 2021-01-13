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
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Un Director è un server che esegue Skype for Business Server 2015 Communications software in grado di autenticare le richieste degli utenti, ma non gli account utente.
ms.openlocfilehash: 76315e9f63e1121119f3823187c379985c4914f0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834936"
---
# <a name="director-planning-tool"></a>Director (strumento di pianificazione)
 
Un Director è un server che esegue Skype for Business Server 2015 Communications software in grado di autenticare le richieste degli utenti, ma non gli account utente. 
  
Questo ruolo è facoltativo, è possibile scegliere di distribuire un Director nei due scenari seguenti:
  
- Se si Abilita l'accesso da parte di utenti esterni tramite la distribuzione di server perimetrali, è necessario distribuire anche un Director. In questo scenario, il Director esegue l'autenticazione degli utenti esterni e quindi passa il traffico ai server interni. Quando un amministratore viene utilizzato per autenticare gli utenti esterni, allevia i server del pool Front end dall'overhead dell'esecuzione dell'autenticazione di tali utenti. Consente inoltre di isolare i pool Front end interni da traffico dannoso, ad esempio attacchi Denial of Service. Se la rete è inondata da traffico esterno non valido durante un attacco di questo tipo, il traffico termina nel Director.
    
- Se si distribuiscono più pool Front end in un sito centrale, aggiungendo un Director al sito è possibile semplificare le richieste di autenticazione e migliorare le prestazioni. In questo scenario, tutte le richieste passano prima al server Director, che le instrada al pool Front end corretto.
    

