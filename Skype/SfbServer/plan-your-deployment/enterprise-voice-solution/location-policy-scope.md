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
description: Pianificazione dei criteri percorso per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: b56b3fa2205939b458635d5a461dc4f8d55134cf2703ce1872a2be2141d5d635
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286505"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>Assegnare l'ambito dei criteri percorso in Skype for Business Server
 
Pianificazione dei criteri percorso per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale.
  
Come per altri Skype for Business Server, i criteri percorso possono essere assegnati a più livelli di ambito: globale, sito e utente. Tuttavia, l'ambito dei criteri percorso a livello di utente si comporta in modo leggermente diverso rispetto ad altri criteri Skype for Business Server utente. Non solo i criteri percorso per utente possono essere applicati agli oggetti endpoint (ad esempio utenti e oggetti contatto di area comune Telefono), ma possono anche essere applicati Skype for Business Server siti di rete. I siti di rete sono raggruppamenti di subnet client associate a una posizione geografica ,ma potrebbero non essere necessariamente tutte subnet in un intero sito centrale o in un sito di succursale. Tutti i client connessi alle subnet in un sito di rete prelevano automaticamente il criterio percorso assegnato a tale sito di rete. Nei casi in cui un criterio percorso a livello di utente viene assegnato sia a un utente che a un sito di rete, il criterio percorso basato sul sito di rete sostituisce qualsiasi impostazione di criterio per utente.
  
A ogni sito di rete è assegnato un criterio percorso e a ogni criterio saranno assegnati valori diversi per Utilizzi PSTN, URI di notifica e URI conferenza.
  
> [!NOTE]
> Il motivo di questo particolare comportamento di ambito dei criteri è che quando un utente che si trova in un pool in un sito di office visita un altro sito e deve effettuare una chiamata di emergenza, le impostazioni di routing delle chiamate E9-1-1 appropriate a tale sito di rete verranno applicate indipendentemente dal pool o dal sito a cui è assegnato l'utente. 
  

