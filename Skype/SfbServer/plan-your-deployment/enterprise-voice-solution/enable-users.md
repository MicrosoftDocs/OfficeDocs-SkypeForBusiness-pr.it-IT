---
title: Abilitare gli utenti per il servizio E9-1-1 in Skype for Business Server
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
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Decisioni necessarie per i criteri percorso per una distribuzione E9-1-1 in Skype for Business Server VoIP aziendale, tra cui quali utenti abilitare e come supportare gli utenti mobili.
ms.openlocfilehash: 9a2ced694357b9225555a05c10e93a1006a771b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825746"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Abilitare gli utenti per il servizio E9-1-1 in Skype for Business Server
 
Decisioni necessarie per i criteri percorso per una distribuzione E9-1-1 in Skype for Business Server VoIP aziendale, tra cui quali utenti abilitare e come supportare gli utenti mobili.
  
Durante la registrazione del client, Skype for Business Server usa un criterio percorso per configurare le proprietà E9-1-1 per VoIP aziendale utenti abilitati. In un criterio percorso sono contenute tutte le impostazioni che definiscono come verrà implementata la funzionalità E9-1-1. Ad esempio, il criterio percorso contiene informazioni come la stringa di composizione per gli interventi di emergenza e indica se un utente deve o meno immettere manualmente una posizione se il servizio informazioni sulla posizione non ne fornisce automaticamente una. Per una definizione completa dei criteri percorso, vedere [Pianificare i criteri percorso per Skype for Business Server.](location-policies.md)
  
Skype for Business Server può assegnare un criterio percorso ai client in base alla subnet o agli utenti in base a criteri globali, per sito o per utente. Per decidere come abilitare gli utenti, è consigliabile innanzitutto tenere conto degli aspetti seguenti.
  
 **Valutare se si prevede di abilitare tutti gli utenti o di limitare il supporto a specifiche aree geografiche dell'organizzazione**
  
> È possibile assegnare una posizione a tutti gli utenti dell'organizzazione utilizzando un criterio percorso globale. Tuttavia, assegnando un criterio percorso a un sito di rete Skype for Business Server e quindi aggiungendo subnet al sito, è possibile limitare il supporto E9-1-1 a posizioni selezionate all'interno dell'organizzazione e specificare il comportamento di routing E9-1-1 per ogni sito. 
    
 **Valutare se si prevede di abilitare singoli utenti mediante un criterio utente**
  
> È possibile assegnare criteri percorso direttamente a utenti specifici o a oggetti contatto di telefoni di area comune se si desidera personalizzare il relativo supporto E9-1-1.
    
 **Valutare se abilitare per E9-1-1 i client che effettuano il roaming all'esterno della rete o si connettono da una subnet non definita**
  
> Se agli utenti viene assegnato un criterio percorso globale, sito o per utente, può essere necessario immettere manualmente una posizione nel client se il client non si trova all'interno di una subnet definita o se non è stata trovata alcuna posizione dal servizio informazioni percorso. Per informazioni dettagliate, vedere [Definire l'esperienza utente per l'acquisizione manuale](manually-acquiring-a-location.md)di una posizione in Skype for Business Server.
    

