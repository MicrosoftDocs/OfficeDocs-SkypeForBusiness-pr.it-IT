---
title: Skype for Business Server Strumento di pianificazione director
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
ms.localizationpriority: medium
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Un Director è un server che Skype for Business Server software di comunicazione 2015 in grado di autenticare le richieste degli utenti, ma non ospita alcun account utente.
ms.openlocfilehash: 3e28c88621d200517ec64e109ea94bc09a442218
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602671"
---
# <a name="skype-for-business-server-director-planning-tool"></a>Skype for Business Server Strumento di pianificazione director
 
Un Director è un server che Skype for Business Server software di comunicazione 2015 in grado di autenticare le richieste degli utenti, ma non ospita alcun account utente. 
  
Questo ruolo è facoltativo, è possibile scegliere di distribuire un Director nei due scenari seguenti:
  
- Se si abilita l'accesso da parte degli utenti guest distribuendo server perimetrali, è consigliabile distribuire anche un Director. In questo scenario, il Director autentica i guest e quindi passa il traffico ai server interni. Quando un Director viene utilizzato per autenticare guest, allevia i server del pool Front End dall'overhead dovuto all'autenticazione di questi utenti. Consente inoltre di isolare i pool Front End interni da traffico dannoso, ad esempio attacchi Denial of Service. Se la rete è inondata da traffico esterno non valido durante un attacco di questo tipo, il traffico termina nel Director.
    
- Se si distribuiscono più pool Front End in un sito centrale, aggiungendo un Director a tale sito è possibile semplificare le richieste di autenticazione e migliorare le prestazioni. In questo scenario, tutte le richieste vengono inviate prima al Server Director, che quindi le instrada al pool Front End corretto.
    

