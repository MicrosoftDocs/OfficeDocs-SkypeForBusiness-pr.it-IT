---
title: User Impostazioni Service for Call Quality Dashboard (CQD)
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
description: "Riepilogo: informazioni sul servizio di Impostazioni utente, che fa parte dell'API repository per il dashboard qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: c037024c8fe336c3614dd9daf6ee02370337ad5c6c44b45c783044cc421f626f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315562"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>User Impostazioni Service for Call Quality Dashboard (CQD)
 
**Riepilogo:** Informazioni sul servizio di Impostazioni utente, che fa parte dell'API repository per il dashboard qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
Il servizio di Impostazioni utente fa parte dell'API repository per il dashboard qualità delle chiamate.
  
## <a name="user-settings-service"></a>Servizio impostazioni utente

Le impostazioni utente sono coppie chiave-valore che le applicazioni possono utilizzare per archiviare metadati per vari scopi, tra cui la personalizzazione dei comportamenti delle applicazioni per utente. Ogni utente riceve un archivio per le impostazioni utente. Solo i proprietari possono aggiungere, modificare e rimuovere le impostazioni utente.
  
 **Global Impostazioni**
  
Le impostazioni globali sono le impostazioni utente di proprietà dell'utente di sistema e tutti gli utenti hanno accesso in sola lettura. Le impostazioni globali sono costanti: vengono create durante la creazione del repository e non cambiano mai.
  
Ogni utente può ignorare le impostazioni globali creando impostazioni utente con le stesse chiavi. Quando l'applicazione richiede le impostazioni utente effettive, l'API restituisce un set di impostazioni globali unite alle impostazioni utente, con ogni impostazione utente che sostituisce la rispettiva impostazione globale se le chiavi sono uguali. L'API può anche restituire solo le impostazioni utente in modo che le applicazioni possano individuare quali impostazioni vengono ignorate. 
  
Le operazioni REST sono incluse nella tabella seguente.

|**Operazione**|**Descrizione**|
|:-----|:-----|
|[Ottieni impostazioni utente](get-user-settings.md) <br/> |Get User Impostazioni restituisce un elenco di impostazioni per un utente specificato.  <br/> |
|[Ottieni impostazione utente](get-user-setting.md) <br/> |Get User Setting restituisce un'impostazione utente singola.  <br/> |
   

