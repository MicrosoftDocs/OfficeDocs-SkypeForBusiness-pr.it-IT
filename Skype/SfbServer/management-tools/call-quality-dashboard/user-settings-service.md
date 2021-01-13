---
title: Servizio impostazioni utente per il dashboard qualità chiamata (CQD)
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
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: "Riepilogo: informazioni sul servizio impostazioni utente, che fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 2b2fc9810f1eceb74974dc105263b0bdcf37ae01
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803037"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>Servizio impostazioni utente per il dashboard qualità chiamata (CQD)
 
**Riepilogo:** Informazioni sul servizio impostazioni utente, che fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.
  
Il servizio impostazioni utente fa parte dell'API del repository per il dashboard qualità chiamata.
  
## <a name="user-settings-service"></a>Servizio impostazioni utente

Le impostazioni utente sono coppie chiave-valore che le applicazioni possono utilizzare per archiviare i metadati per diversi scopi, inclusa la personalizzazione dei comportamenti dell'applicazione per utente. Ogni utente riceve un archivio per le impostazioni utente. Solo i proprietari possono aggiungere, modificare e rimuovere le impostazioni dell'utente.
  
 **Impostazioni globali**
  
Le impostazioni globali sono le impostazioni utente di proprietà dell'utente del sistema e tutti gli utenti dispongono dell'accesso in sola lettura. Le impostazioni globali sono costanti: vengono create durante la creazione del repository e non cambiano mai.
  
Ogni utente può eseguire l'override delle impostazioni globali creando le impostazioni utente con le stesse chiavi. Quando l'applicazione richiede le impostazioni utente effettive, l'API restituisce un insieme di impostazioni globali unite alle impostazioni utente, con ogni impostazione che sostituisce l'impostazione globale corrispondente se le chiavi sono uguali. L'API può anche restituire solo le impostazioni utente in modo che le applicazioni possano scoprire quali impostazioni sono sottoposte a override. 
  
Le operazioni REST sono incluse nella tabella seguente.

|**Operazione**|**Descrizione**|
|:-----|:-----|
|[Ottieni impostazioni utente](get-user-settings.md) <br/> |Ottenere le impostazioni utente restituisce un elenco di impostazioni per un utente specificato.  <br/> |
|[Ottieni impostazione utente](get-user-setting.md) <br/> |Ottenere l'impostazione utente restituisce una singola impostazione utente.  <br/> |
   

