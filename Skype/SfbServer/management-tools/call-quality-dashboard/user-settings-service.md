---
title: User Impostazioni Service for Call Quality Dashboard (CQD)
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: "Riepilogo: informazioni sul servizio di Impostazioni utente, che fa parte dell'API repository per il dashboard di qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 81abbc31a82fc696a5bcb45faf4120b71fc26f74
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856583"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>User Impostazioni Service for Call Quality Dashboard (CQD)
 
**Riepilogo:** Informazioni sul servizio di Impostazioni utente, che fa parte dell'API repository per il dashboard di qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
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
   

