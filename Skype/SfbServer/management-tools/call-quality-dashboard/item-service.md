---
title: Servizio elementi per il dashboard qualità chiamata (CQD)
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
description: "Riepilogo: informazioni sul servizio elementi, che fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: b904f814a837af13e4015af5fbaca924739b8997
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827706"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>Servizio elementi per il dashboard qualità chiamata (CQD)
 
**Riepilogo:** Informazioni sul servizio elementi, che fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.
  
Il servizio elementi fa parte dell'API del repository per il dashboard qualità chiamata.
  
## <a name="item-service"></a>Servizio elementi

L'API del repository offre un servizio di gestione dei contenuti semplice, noto come servizio elementi, che può essere utilizzato per archiviare qualsiasi contenuto definito dall'applicazione per gli utenti. 
  
Il contenuto del sistema è di proprietà dell'utente del sistema e condiviso da tutti gli utenti con accesso in sola lettura. I contenuti degli utenti dedicati sono di proprietà di utenti regolari e solo i proprietari possono modificarli o eliminarli, ma tutti gli utenti hanno ancora accesso in sola lettura.
  
> [!NOTE]
> Questa documentazione dell'API riguarda le operazioni di sola lettura dell'API del repository. 
  
Call Quality dashboard consente di salvare i report e le query come elementi nel database del repository. Un elemento può avere voci secondarie facoltative e il dashboard qualità chiamata organizza i report e le query in una struttura gerarchica utilizzando la caratteristica elementi secondari.
  
Il servizio elementi include i concetti seguenti:
  
- **Elemento** -elemento di base del repository. Ogni elemento è di proprietà di un solo utente.
    
- **Elemento secondario** -la meccanica organizzativa di base del repository. L'elemento può avere zero, uno o più elementi subordinati.
    
- Elementi **antenati** : l'elenco degli elementi, a partire dall'elemento in primo piano, che è l'elemento predefinito dell'utente, che porta a un determinato elemento.
    
- **Contenuto dell'elemento** -contenuto specifico dell'applicazione archiviato negli elementi. Call Quality dashboard consente di salvare le rappresentazioni JSON dei report e delle query nei contenuti.
    
Le operazioni REST sono incluse nella tabella seguente.
  

|**Operazione**|**Descrizione**|
|:-----|:-----|
|[Ottenere elementi](get-items.md) <br/> |Gli elementi Get restituiscono tutti gli elementi nell'archivio.  <br/> |
|[Ottieni elemento](get-item.md) <br/> |L'elemento Get restituisce un elemento specifico.  <br/> |
|[Ottieni elementi secondari](get-sub-items.md) <br/> |Get Sub-Items restituisce gli elementi secondari di un elemento specifico.  <br/> |
|[Ottieni predecessori elemento](get-item-ancestors.md) <br/> |Ottenere gli antenati degli elementi restituisce gli antenati di un elemento specifico.  <br/> |
|[Aggiorna elemento](update-item.md) <br/> |Aggiornare un elemento specifico nell'archivio.  <br/> |
   

