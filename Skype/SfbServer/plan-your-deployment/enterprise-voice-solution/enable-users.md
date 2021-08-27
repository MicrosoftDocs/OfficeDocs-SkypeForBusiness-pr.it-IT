---
title: Abilitare gli utenti per E9-1-1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Decisioni necessarie per i criteri percorso per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale, inclusi gli utenti da abilitare e come supportare gli utenti mobili.
ms.openlocfilehash: 6a28a27942c93f20aa9b96fcf3b94e554602527c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598750"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Abilitare gli utenti per E9-1-1 in Skype for Business Server
 
Decisioni necessarie per i criteri percorso per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale, inclusi gli utenti da abilitare e come supportare gli utenti mobili.
  
Durante la registrazione del client, Skype for Business Server criteri percorso per configurare le proprietà E9-1-1 per VoIP aziendale utenti abilitati. In un criterio percorso sono contenute tutte le impostazioni che definiscono come verrà implementata la funzionalità E9-1-1. Ad esempio, il criterio percorso contiene informazioni come la stringa di composizione di emergenza e indica se un utente deve immettere manualmente una posizione se il servizio informazioni sulla posizione non ne fornisce automaticamente una. Per una definizione completa di un criterio percorso, vedere [Plan location policies for Skype for Business Server](location-policies.md).
  
Skype for Business Server può assegnare un criterio percorso ai client in base alla subnet o agli utenti in base a un criterio globale, per sito o per utente. Per decidere come abilitare gli utenti, è consigliabile innanzitutto tenere conto degli aspetti seguenti.
  
 **Valutare se si prevede di abilitare tutti gli utenti o di limitare il supporto a specifiche aree geografiche dell'organizzazione**
  
> È possibile assegnare una posizione a tutti gli utenti dell'organizzazione utilizzando un criterio percorso globale. Tuttavia, assegnando un criterio percorso a un sito di rete di Skype for Business Server e quindi aggiungendo subnet al sito, è possibile limitare il supporto E9-1-1 a posizioni selezionate all'interno dell'organizzazione e specificare il comportamento di routing E9-1-1 in base al sito. 
    
 **Valutare se si prevede di abilitare singoli utenti mediante un criterio utente**
  
> È possibile assegnare criteri percorso direttamente a utenti specifici o a oggetti contatto di telefoni di area comune se si desidera personalizzare il relativo supporto E9-1-1.
    
 **Valutare se abilitare per E9-1-1 i client che effettuano il roaming all'esterno della rete o si connettono da una subnet non definita**
  
> Se agli utenti viene assegnato un criterio percorso globale, sito o per utente, può essere necessario immettere manualmente una posizione nel client se il client non si trova all'interno di una subnet definita o se il servizio informazioni percorso non ha trovato alcuna posizione. Per informazioni dettagliate, [vedere Define the user experience for manually acquiring a location in Skype for Business Server.](manually-acquiring-a-location.md)
    

