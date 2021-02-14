---
title: Item Service for Call Quality Dashboard (CQD)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: "Riepilogo: informazioni su Item Service, che fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: b904f814a837af13e4015af5fbaca924739b8997
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827706"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Item Service for Call Quality Dashboard (CQD)
 
**Riepilogo:** Informazioni su Item Service, che fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
Item Service fa parte dell'API repository per call quality dashboard.
  
## <a name="item-service"></a>Servizio elementi

L'API repository offre un semplice servizio di gestione del contenuto, noto come servizio elementi, che può essere usato per archiviare qualsiasi contenuto definito dall'applicazione per gli utenti. 
  
Il contenuto del sistema è di proprietà dell'utente di sistema e condiviso da tutti gli utenti con accesso in sola lettura. I contenuti degli utenti dedicati sono di proprietà di utenti normali e solo i proprietari possono modificarli o eliminarli, ma tutti gli utenti hanno ancora accesso in sola lettura.
  
> [!NOTE]
> Questa documentazione dell'API illustra le operazioni di sola lettura dell'API repository. 
  
Il dashboard qualità delle chiamate salva i rapporti e le query come elementi nel database repository. Un elemento può avere elementi secondari facoltativi e call quality dashboard organizza report e query in una struttura gerarchica utilizzando la funzionalità elementi secondari.
  
Il servizio elementi include i concetti seguenti:
  
- **Elemento** : l'elemento di base del repository. Ogni elemento è di proprietà esattamente di un utente.
    
- **Sotto-elemento:** le meccaniche organizzative di base dell'archivio. L'elemento può avere zero, uno o più elementi subordinati.
    
- **Predecessori elemento** - Elenco di elementi, a partire dall'elemento più in alto, che è l'elemento predefinito dell'utente, che conduce a un determinato elemento.
    
- **Contenuto elemento:** il contenuto specifico dell'applicazione archiviato in Elementi. Call Quality Dashboard salva le rappresentazioni JSON di report e query nel contenuto.
    
Le operazioni REST sono incluse nella tabella seguente.
  

|**Operazione**|**Descrizione**|
|:-----|:-----|
|[Ottenere elementi](get-items.md) <br/> |Il metodo Get Items restituisce tutti gli elementi nel repository.  <br/> |
|[Ottieni elemento](get-item.md) <br/> |Get Item restituisce un elemento specifico.  <br/> |
|[Ottieni elementi secondari](get-sub-items.md) <br/> |Ottiene Sub-Items restituisce gli elementi secondari di un elemento specifico.  <br/> |
|[Ottieni predecessori elemento](get-item-ancestors.md) <br/> |Get Item Predecessors restituisce i predecessori di un elemento specifico.  <br/> |
|[Aggiorna elemento](update-item.md) <br/> |Aggiornare un elemento specifico nel repository.  <br/> |
   

