---
title: Abilitare gli utenti per E9-1-1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Decisioni necessarie per i criteri di posizione per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale, inclusi gli utenti da abilitare e come supportare gli utenti mobili.
ms.openlocfilehash: 1e714e5296e8176c9052b50a5d4ce4f2c0d6184b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187706"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Abilitare gli utenti per E9-1-1 in Skype for Business Server
 
Decisioni necessarie per i criteri di posizione per una distribuzione di E9-1-1 in Skype for Business Server VoIP aziendale, inclusi gli utenti da abilitare e come supportare gli utenti mobili.
  
Durante la registrazione del client, Skype for Business Server usa un criterio di posizione per configurare le proprietà di E9-1-1 per gli utenti abilitati per VoIP aziendale. Questo criterio contiene le impostazioni che definiscono la modalità di implementazione di E9-1-1. Ad esempio, il criterio di posizione contiene informazioni come la stringa di chiamata di emergenza e se un utente deve immettere manualmente una posizione se il servizio informazioni sulla posizione non ne fornisce automaticamente uno. Per una definizione completa dei criteri di posizione, vedere [pianificare i criteri di posizione per Skype for Business Server](location-policies.md).
  
Skype for Business Server può assegnare un criterio di posizione ai client in base alla subnet o agli utenti in base a un criterio globale, per sito o per utente. Per decidere come abilitare gli utenti, è necessario prima rispondere alle domande seguenti.
  
 **Si prevede di abilitare tutti gli utenti o di limitare il supporto a specifiche aree geografiche dell'organizzazione?**
  
> È possibile assegnare una posizione a tutti gli utenti dell'organizzazione usando un criterio di posizione globale. Tuttavia, assegnando un criterio di posizione a un sito di rete di Skype for Business Server e aggiungendo subnet al sito, è possibile limitare il supporto di E9-1-1 ai percorsi selezionati all'interno dell'organizzazione e specificare il comportamento di routing del servizio E9-1-1 per ogni singolo sito. 
    
 **Si prevede di abilitare singoli utenti tramite un criterio utente?**
  
> Per personalizzare il supporto di E9-1-1, è possibile assegnare i criteri di posizione direttamente a utenti specifici o oggetti contatto telefonico di area comune.
    
 **Quando i client vagano all'esterno della rete o si connettono da una subnet non definita, i client devono essere ancora abilitati per E9-1-1?**
  
> Se agli utenti viene assegnato un criterio di posizione globale, sito o per utente, è possibile che sia necessario immettere manualmente una posizione nel client se il client non si trova all'interno di una subnet definita o se il servizio informazioni sulla posizione non è stato trovato. Per informazioni dettagliate, vedere [definire l'esperienza utente per l'acquisizione manuale di una posizione in Skype for Business Server](manually-acquiring-a-location.md).
    

