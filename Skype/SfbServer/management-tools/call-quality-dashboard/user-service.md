---
title: Servizio utente per CQD
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
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: "Riepilogo: informazioni sul servizio utente, che fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: d9f4b771a1bf5efeece4f8fb87195d8567f0426e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803076"
---
# <a name="user-service-for-cqd"></a>Servizio utente per CQD
 
**Riepilogo:** Informazioni sul servizio utente, che fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.
  
Il servizio utente fa parte dell'API del repository per il dashboard qualità chiamata.
  
## <a name="user-service"></a>Servizio utente

L'API del repository fornisce un modello semplificato per la gestione degli utenti in cui il provisioning degli utenti (creazione di nuovi account utente) è automatico e implicito. Quando un utente effettua una richiesta per l'API di repository per la prima volta, viene creato un nuovo record utente. 
  
Call Quality dashboard consente inoltre di creare automaticamente gli elementi dedicati all'utente per il nuovo utente. I nuovi elementi dedicati all'utente sono cloni completi degli elementi dell'utente del sistema. In questo modo, gli utenti iniziano con le proprie copie dei report e delle query che possono immediatamente avviare la personalizzazione. 
  
> [!NOTE]
> Usando dashboard qualità chiamata, gli utenti possono reimpostare gli elementi dedicati in qualsiasi momento. 
  
 **ID utente speciali**
  
L'API del repository include gli URI dell'API REST che prevedono un valore intero per specificare un utente specifico. Esempio:  `https://<portal>/QoERepositoryService/repository/user/{userId}` . In questo caso, {userId} deve essere sostituito da un valore intero, ad esempio 0, 1 e così via.
  
Inoltre, l'API del repository accetterà due ID utente speciali su {userId} in URI.
  
-  *default*  : rappresenta l'utente che sta interagendo con l'API. In questo modo le applicazioni possono accedere al contenuto dell'utente corrente senza tenere conto del valore effettivo dell'ID utente. Esempio: `https://<portal>/QoERepositoryService/repository/user/default` .
    
-  *System*  : rappresenta l'utente del sistema. In questo modo le applicazioni possono accedere al contenuto dell'utente del sistema senza conoscere il valore effettivo dell'ID utente. Esempio: `https://<portal>/QoERepositoryService/repository/user/system` .
    
Se non diversamente specificato, gli ID utente speciali possono essere utilizzati in {userId} in URI. 
  
Le operazioni REST sono incluse nella tabella seguente.
  
|**Operazione**|**Descrizione**|
|:-----|:-----|
|[Ottieni utenti](get-users.md) <br/> |Restituisce un elenco di utenti nel repository.  <br/> |
|[Ottieni utente](get-user.md) <br/> |Restituisce un record utente.  <br/> |
   

