---
title: Assegnazione dell'ambito dei criteri percorso in Skype for Business Server
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
description: Pianificare i criteri percorso per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 586aabe919ea4236dc724446da717b5f300d88e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825526"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>Assegnazione dell'ambito dei criteri percorso in Skype for Business Server
 
Pianificare i criteri percorso per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.
  
Come per gli altri criteri di Skype for Business Server, i criteri di percorso possono essere assegnati a più livelli di ambito: globale, sito e utente. Tuttavia, l'ambito dei criteri percorso a livello di utente si comporta in modo diverso rispetto ad altri criteri di Skype for Business Server. Non solo i criteri percorso per utente possono essere applicati agli oggetti endpoint (come gli utenti e gli oggetti contatto telefonici di area comune), che possono essere applicati anche ai siti di rete di Skype for Business Server. I siti di rete sono raggruppamenti di subnet client associati a una posizione geografica (ma potrebbero non essere necessariamente tutte le subnet di un intero sito centrale o di un sito di succursale). Tutti i client connessi alle subnet in un sito di rete raccolgono automaticamente il criterio percorso assegnato al sito di rete. Nei casi in cui un criterio percorso a livello di utente sia assegnato a un utente e a un sito di rete, il criterio percorso basato sul sito di rete sostituisce qualsiasi impostazione di criteri per utente.
  
A ogni sito di rete è assegnato un criterio percorso e ogni criterio avrà diversi utilizzi PSTN, URI di notifica e valori URI di conferenza assegnati.
  
> [!NOTE]
> Il motivo di questo comportamento di ambito dei criteri speciali è tale che quando un utente ospitato in un pool di un sito di Office visita un altro sito e deve effettuare una chiamata di emergenza, le impostazioni di routing delle chiamate di E9-1-1 appropriate per il sito di rete verranno applicate indipendentemente dal pool o dal sito a cui l'utente è assegnato. 
  

