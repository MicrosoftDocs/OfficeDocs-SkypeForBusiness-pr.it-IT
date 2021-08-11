---
title: Strumento di pianificazione director
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
description: Un Director è un server che Skype for Business Server software di comunicazione 2015 in grado di autenticare le richieste degli utenti ma non ospita alcun account utente.
ms.openlocfilehash: c6f1a9a16d8d97888be4b9453a7ce3746298cce4cf38beebcf82ff2f89e77904
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54283258"
---
# <a name="director-planning-tool"></a>Strumento di pianificazione director
 
Un Director è un server che esegue Skype for Business Server 2015 che può autenticare le richieste degli utenti, ma non ospita alcun account utente. 
  
Questo ruolo è facoltativo, è possibile scegliere di distribuire un Director nei due scenari seguenti:
  
- Se si abilita l'accesso da parte degli utenti guest distribuendo i server perimetrali, è consigliabile distribuire anche un Director. In questo scenario, il director autentica i guest e quindi passa il traffico ai server interni. Quando un Director viene utilizzato per autenticare gli utenti guest, allevia i server del pool Front End dall'overhead dovuto all'autenticazione di questi utenti. Consente inoltre di isolare i pool Front End interni da traffico dannoso, ad esempio attacchi Denial of Service. Se la rete è inondata da traffico esterno non valido durante un attacco di questo tipo, il traffico termina nel Director.
    
- Se si distribuiscono più pool Front End in un sito centrale, aggiungendo un Director a tale sito è possibile semplificare le richieste di autenticazione e migliorare le prestazioni. In questo scenario, tutte le richieste vengono inviate prima al Server Director, che quindi le instrada al pool Front End corretto.
    

