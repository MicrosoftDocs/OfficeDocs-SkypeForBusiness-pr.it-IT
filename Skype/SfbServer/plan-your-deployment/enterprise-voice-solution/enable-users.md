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
description: Le decisioni necessarie per i criteri percorso per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale, compresi gli utenti che consentono di abilitare e come supportare gli utenti di roaming.
ms.openlocfilehash: 9a2ced694357b9225555a05c10e93a1006a771b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825746"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Abilitare gli utenti per il servizio E9-1-1 in Skype for Business Server
 
Le decisioni necessarie per i criteri percorso per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale, compresi gli utenti che consentono di abilitare e come supportare gli utenti di roaming.
  
Durante la registrazione dei client, in Skype for Business Server viene utilizzato un criterio percorso per configurare le proprietà di E9-1-1 per gli utenti abilitati per VoIP aziendale. In un criterio percorso sono contenute tutte le impostazioni che definiscono come verrà implementata la funzionalità E9-1-1. Ad esempio, il criterio percorso contiene informazioni quali la stringa di chiamata di emergenza e se un utente è tenuto a immettere manualmente una posizione se il servizio informazioni percorso non ne fornisce automaticamente una. Per una definizione completa dei criteri percorso, vedere [Plan location Policies for Skype for Business Server](location-policies.md).
  
Skype for Business Server è in grado di assegnare un criterio percorso ai client in base alla subnet o agli utenti in base a criteri globali, per sito o per utente. Per decidere come abilitare gli utenti, è consigliabile innanzitutto tenere conto degli aspetti seguenti.
  
 **Valutare se si prevede di abilitare tutti gli utenti o di limitare il supporto a specifiche aree geografiche dell'organizzazione**
  
> È possibile assegnare una posizione a tutti gli utenti dell'organizzazione utilizzando un criterio percorso globale. Tuttavia, assegnando un criterio percorso a un sito di rete di Skype for Business Server e quindi aggiungendo subnet al sito, è possibile limitare il supporto di E9-1-1 ai percorsi selezionati all'interno dell'organizzazione e specificare il comportamento di routing di E9-1-1 per ogni singolo sito. 
    
 **Valutare se si prevede di abilitare singoli utenti mediante un criterio utente**
  
> È possibile assegnare criteri percorso direttamente a utenti specifici o a oggetti contatto di telefoni di area comune se si desidera personalizzare il relativo supporto E9-1-1.
    
 **Valutare se abilitare per E9-1-1 i client che effettuano il roaming all'esterno della rete o si connettono da una subnet non definita**
  
> Se agli utenti viene assegnato un criterio percorso globale, sito o per utente, è possibile che venga richiesto di immettere manualmente una posizione nel client se il client non si trova all'interno di una subnet definita o se il servizio informazioni percorso non è stato trovato. Per ulteriori informazioni, vedere [definire l'esperienza utente per l'acquisizione manuale di una posizione in Skype for Business Server](manually-acquiring-a-location.md).
    

