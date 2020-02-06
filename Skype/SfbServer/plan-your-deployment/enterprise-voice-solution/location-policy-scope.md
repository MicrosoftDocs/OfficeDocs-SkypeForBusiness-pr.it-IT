---
title: Assegnare l'ambito dei criteri di posizione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Pianificazione dei criteri di posizione per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 3865db146676ed64da9422d2a8731e44451ec6ac
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802756"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>Assegnare l'ambito dei criteri di posizione in Skype for Business Server
 
Pianificazione dei criteri di posizione per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.
  
Come per altri criteri di Skype for Business Server, i criteri di posizione possono essere assegnati a più livelli di ambito: globale, sito e utente. Tuttavia, l'ambito dei criteri di posizione a livello di utente si comporta in modo diverso rispetto a quello di altri criteri di Skype for Business Server. Non solo i criteri di posizione per utente possono essere applicati agli oggetti endpoint, ad esempio gli utenti e gli oggetti di contatto telefonico per l'area comune, ma possono essere applicati anche ai siti di rete di Skype for Business Server. I siti di rete sono raggruppamenti di subnet client associati a una posizione geografica (ma potrebbero non essere necessariamente tutte le subnet di un intero sito centrale o di un sito di succursale). Tutti i client connessi alle subnet in un sito di rete prelevano automaticamente i criteri di posizione assegnati al sito di rete. Nei casi in cui un criterio di posizione a livello di utente viene assegnato sia a un utente che a un sito di rete, il criterio di posizione basato sul sito di rete sostituisce qualsiasi impostazione di criteri per utente.
  
A ogni sito di rete è assegnato un criterio di posizione e ogni criterio avrà diversi usi PSTN, URI di notifica e valori degli URI di conferenza assegnati.
  
> [!NOTE]
> Il motivo di questo comportamento speciale per l'ambito dei criteri è che quando un utente ospitato in un pool di un sito di Office visita un altro sito e deve effettuare una chiamata di emergenza, le impostazioni di routing delle chiamate di E9-1-1 appropriate per il sito di rete verranno applicate indipendentemente dal pool o dal sito che si usa viene assegnato a ser. 
  

