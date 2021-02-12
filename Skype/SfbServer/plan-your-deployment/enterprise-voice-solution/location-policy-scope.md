---
title: Assegnare l'ambito dei criteri percorso in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Pianificazione dei criteri percorso per una distribuzione E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 586aabe919ea4236dc724446da717b5f300d88e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825526"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>Assegnare l'ambito dei criteri percorso in Skype for Business Server
 
Pianificazione dei criteri percorso per una distribuzione E9-1-1 in Skype for Business Server VoIP aziendale.
  
Come per altri criteri di Skype for Business Server, i criteri percorso possono essere assegnati a più livelli di ambito: globale, sito e utente. Tuttavia, l'ambito dei criteri percorso a livello di utente si comporta in modo leggermente diverso rispetto ad altri criteri di Skype for Business Server. Non solo i criteri percorso per utente possono essere applicati agli oggetti endpoint (ad esempio gli utenti e gli oggetti contatto del telefono dell'area comune), ma anche ai siti di rete di Skype for Business Server. I siti di rete sono raggruppamenti di subnet client associate a una posizione geografica (ma potrebbero non essere necessariamente tutte subnet in un intero sito centrale o in un sito di succursale). Tutti i client connessi alle subnet in un sito di rete selezionano automaticamente i criteri percorso assegnati a tale sito di rete. Nei casi in cui un criterio percorso a livello di utente viene assegnato sia a un utente che a un sito di rete, il criterio percorso basato sul sito di rete sostituisce qualsiasi impostazione dei criteri per utente.
  
A ogni sito di rete è assegnato un criterio percorso e a ogni criterio saranno assegnati valori diversi di Utilizzi PSTN, URI di notifica e URI conferenza.
  
> [!NOTE]
> Il motivo di questo particolare comportamento di ambito dei criteri è che quando un utente che si trova in un pool in un sito dell'ufficio visita un altro sito e deve effettuare una chiamata di emergenza, le impostazioni di routing delle chiamate E9-1-1 appropriate per tale sito di rete verranno applicate indipendentemente dal pool o dal sito a cui è assegnato l'utente. 
  

