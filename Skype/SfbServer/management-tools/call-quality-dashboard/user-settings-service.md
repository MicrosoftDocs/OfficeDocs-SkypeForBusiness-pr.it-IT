---
title: Servizio impostazioni utente per dashboard qualità chiamata (Call Quality Dashboard)
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
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: "Riepilogo: informazioni sul servizio impostazioni utente, che fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 1eef869523bf1590a00ca199727b33ec9e13ccba
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816645"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>Servizio impostazioni utente per dashboard qualità chiamata (Call Quality Dashboard)
 
**Riepilogo:** Informazioni sul servizio impostazioni utente, che fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
Il servizio impostazioni utente fa parte dell'API del repository per il dashboard della qualità delle chiamate.
  
## <a name="user-settings-service"></a>Servizio impostazioni utente

Le impostazioni utente sono coppie chiave-valore che le applicazioni possono usare per archiviare i metadati per diversi scopi, inclusa la personalizzazione dei comportamenti per utente dell'applicazione. Ogni utente riceve un archivio per le impostazioni utente. Solo i proprietari possono aggiungere, modificare e rimuovere le impostazioni utente.
  
 **Impostazioni globali**
  
Le impostazioni globali sono le impostazioni utente di proprietà dell'utente del sistema e tutti gli utenti hanno accesso in sola lettura. Le impostazioni globali sono costanti: vengono create durante la creazione del repository e non cambiano mai.
  
Ogni utente può eseguire l'override delle impostazioni globali creando le impostazioni utente con le stesse chiavi. Quando l'applicazione richiede le impostazioni utente effettive, l'API restituisce un set di impostazioni globali unite alle impostazioni utente, con ogni impostazione utente che sostituisce la rispettiva impostazione globale se i tasti sono gli stessi. L'API può anche restituire solo le impostazioni utente in modo che le applicazioni possano scoprire quali impostazioni vengono ignorate. 
  
Le operazioni REST sono incluse nella tabella seguente.

|**Operazione**|**Descrizione**|
|:-----|:-----|
|[Ottieni impostazioni utente](get-user-settings.md) <br/> |Ottieni impostazioni utente restituisce un elenco di impostazioni per un utente specificato.  <br/> |
|[Ottieni impostazione utente](get-user-setting.md) <br/> |Per ottenere l'impostazione utente viene restituita una singola impostazione utente.  <br/> |
   

