---
title: Servizio voce per dashboard qualità chiamata (Call Quality Dashboard)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: "Riepilogo: informazioni sul servizio elementi, che fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 5fdf2aedcb1a5e8d7d1929d7af70c5911cae46f0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816715"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Servizio voce per dashboard qualità chiamata (Call Quality Dashboard)
 
**Riepilogo:** Informazioni sul servizio elementi, che fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate.
  
## <a name="item-service"></a>Servizio elementi

API del repository offre un semplice servizio di gestione del contenuto, noto come servizio per gli elementi, che può essere usato per archiviare qualsiasi contenuto definito dall'applicazione per gli utenti. 
  
Il contenuto del sistema è di proprietà dell'utente del sistema e condiviso da tutti gli utenti con accesso di sola lettura. I contenuti utente dedicati sono di proprietà di utenti regolari e solo i proprietari possono modificarli o eliminarli, ma tutti gli utenti hanno comunque accesso di sola lettura.
  
> [!NOTE]
> Questa documentazione API riguarda le operazioni di sola lettura dell'API del repository. 
  
Il dashboard qualità chiamata salva i report e le query come elementi nel database del repository. Un elemento può avere elementi secondari facoltativi e il dashboard qualità chiamata organizza report e query in una struttura gerarchica mediante la caratteristica elementi secondari.
  
Il servizio elementi include i concetti seguenti:
  
- **Elemento** -l'elemento di base del repository. Ogni elemento è di proprietà di un solo utente.
    
- **Elemento secondario** : la meccanica organizzativa di base del repository. L'elemento può avere zero, uno o più elementi subordinati.
    
- **Antenati elemento** -l'elenco di elementi, a partire dall'elemento in primo piano, che è l'elemento predefinito dell'utente, che porta a un elemento specifico.
    
- **Contenuto dell'elemento** -contenuto specifico dell'applicazione archiviato in elementi. Il dashboard qualità chiamata consente di salvare le rappresentazioni JSON di report e query in contenuto.
    
Le operazioni REST sono incluse nella tabella seguente.
  

|**Operazione**|**Descrizione**|
|:-----|:-----|
|[Ottenere elementi](get-items.md) <br/> |Get Items restituisce tutti gli elementi del repository.  <br/> |
|[Ottieni elemento](get-item.md) <br/> |Ottieni elemento restituisce un elemento specifico.  <br/> |
|[Ottieni elementi secondari](get-sub-items.md) <br/> |Get Sub-Items restituisce gli elementi secondari di un elemento specifico.  <br/> |
|[Ottieni predecessori elemento](get-item-ancestors.md) <br/> |Ottenere gli antenati degli elementi restituisce gli antenati di un elemento specifico.  <br/> |
|[Aggiorna elemento](update-item.md) <br/> |Aggiornare un elemento specifico nel repository.  <br/> |
   

