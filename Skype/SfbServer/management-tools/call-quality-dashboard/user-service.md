---
title: Servizio utente per CQD
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: "Riepilogo: informazioni sul servizio utente, che fa parte dell'API repository per il dashboard qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: ac709949e9d69dbf92f9c0c185406c7d3d8d5462
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766384"
---
# <a name="user-service-for-cqd"></a>Servizio utente per CQD
 
**Riepilogo:** Informazioni sul servizio utente, che fa parte dell'API repository per il dashboard di qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
Il servizio utente fa parte dell'API repository per il dashboard di qualità delle chiamate.
  
## <a name="user-service"></a>Servizio utente

L'API repository offre un modello di gestione degli utenti semplificato in cui il provisioning degli utenti (creazione di nuovi account utente) è automatico e implicito. Quando un utente effettua una richiesta in base all'API repository per la prima volta, il repository crea un nuovo record Utente. 
  
Call Quality Dashboard crea inoltre automaticamente elementi dedicati all'utente per il nuovo utente. I nuovi elementi dedicati all'utente sono cloni completi degli elementi dell'utente di sistema. In questo modo, gli utenti iniziano con le proprie copie di report e query che possono iniziare immediatamente a personalizzare. 
  
> [!NOTE]
> Usando call quality dashboard, gli utenti possono reimpostare i propri elementi dedicati in qualsiasi momento. 
  
 **ID utente speciali**
  
L'API di repository include URI DELL'API REST che prevedono un valore intero per specificare un utente specifico. Esempio:  `https://<portal>/QoERepositoryService/repository/user/{userId}` . In questo caso, {userId} deve essere sostituito da un valore intero, ad esempio 0, 1 e così via.
  
Inoltre, l'API repository accetterà due ID utente speciali in {userId} negli URI.
  
-  *default*  - rappresenta l'utente che sta attualmente interagendo con l'API. In questo modo le applicazioni possono accedere al contenuto dell'utente corrente senza tenere traccia del valore effettivo dell'ID utente. Esempio: `https://<portal>/QoERepositoryService/repository/user/default` .
    
-  *system*  - rappresenta l'utente del sistema. In questo modo le applicazioni possono accedere al contenuto dell'utente di sistema senza conoscere il valore effettivo dell'ID utente. Esempio: `https://<portal>/QoERepositoryService/repository/user/system` .
    
Se non specificato diversamente, gli ID utente speciali possono essere usati in {userId} negli URI. 
  
Le operazioni REST sono incluse nella tabella seguente.
  
|**Operazione**|**Descrizione**|
|:-----|:-----|
|[Ottieni utenti](get-users.md) <br/> |Restituisce un elenco di utenti nel repository.  <br/> |
|[Ottieni utente](get-user.md) <br/> |Restituisce un record utente.  <br/> |
   

