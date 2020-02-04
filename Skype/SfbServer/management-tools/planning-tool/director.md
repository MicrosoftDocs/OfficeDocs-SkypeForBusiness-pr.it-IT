---
title: Director (strumento di pianificazione)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Un amministratore è un server che esegue Skype for Business Server 2015 Communications software che può autenticare le richieste degli utenti, ma non ospita gli account utente.
ms.openlocfilehash: 48b691262dc638faf6f0aa9910a5adac3c1f0e46
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684249"
---
# <a name="director-planning-tool"></a>Director (strumento di pianificazione)
 
Un amministratore è un server che esegue Skype for Business Server 2015 Communications software che può autenticare le richieste degli utenti, ma non ospita gli account utente. 
  
Questo ruolo è facoltativo, si sceglie di distribuire un Director nei due scenari seguenti:
  
- Se si Abilita l'accesso da parte di utenti esterni distribuendo Edge Server, è anche necessario distribuire un Director. In questo scenario, il Director esegue l'autenticazione degli utenti esterni e quindi passa il traffico ai server interni. Quando un amministratore viene usato per autenticare utenti esterni, allevia i server del pool Front-end dall'overhead dell'esecuzione dell'autenticazione di questi utenti. Consente inoltre di isolare i pool di front-end interni da traffico illecito, ad esempio attacchi Denial of Service. Se la rete viene allagata con traffico esterno non valido in un attacco di questo tipo, il traffico termina con il direttore.
    
- Se si distribuiscono più pool Front-end in un sito centrale, aggiungendo un Director al sito è possibile semplificare le richieste di autenticazione e migliorare le prestazioni. In questo scenario tutte le richieste vanno prima di tutto al Director, che li instrada al pool Front end corretto.
    

