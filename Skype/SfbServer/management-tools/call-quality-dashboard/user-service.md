---
title: Servizio utente per Call Quality dashboard
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: "Riepilogo: informazioni sul servizio utente, che fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 6e0a6a58be98469458a8c8e7063402ff6477c35f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "36195888"
---
# <a name="user-service-for-cqd"></a>Servizio utente per Call Quality dashboard
 
**Riepilogo:** Informazioni sul servizio utente, che fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
Il servizio utente fa parte dell'API del repository per il dashboard della qualità delle chiamate.
  
## <a name="user-service"></a>Servizio utente

L'API del repository offre un modello di gestione semplificato degli utenti in cui il provisioning degli utenti (creazione di nuovi account utente) è automatico e implicito. Quando un utente effettua una richiesta contro l'API del repository per la prima volta, il repository crea un nuovo record utente. 
  
Il dashboard qualità chiamata crea inoltre automaticamente un elemento dedicato agli utenti per il nuovo utente. I nuovi elementi dedicati agli utenti sono cloni completi degli elementi dell'utente del sistema. In questo modo, gli utenti iniziano con le proprie copie di report e query che possono immediatamente iniziare a personalizzare. 
  
> [!NOTE]
> Usando dashboard qualità chiamata, gli utenti possono reimpostare gli elementi dedicati in qualsiasi momento. 
  
 **ID utente speciali**
  
L'API del repository include gli URI delle API REST che prevedono un valore intero per specificare un determinato utente. Esempio: `https://<portal>/QoERepositoryService/repository/user/{userId}`. In questo caso, {userId} deve essere sostituito da un valore intero come 0, 1 e così via.
  
Inoltre, l'API del repository accetterà due ID utente speciali in {userId} in URI.
  
-  *default* : rappresenta l'utente che sta interagendo con l'API. Questo consente alle applicazioni di accedere al contenuto dell'utente corrente senza tenere traccia del valore effettivo dell'ID utente. Esempio: `https://<portal>/QoERepositoryService/repository/user/default`.
    
-  *System* : rappresenta l'utente del sistema. Questo consente alle applicazioni di accedere al contenuto dell'utente del sistema senza conoscere il valore effettivo dell'ID utente. Esempio: `https://<portal>/QoERepositoryService/repository/user/system`.
    
Se non diversamente specificato, gli ID utente speciali possono essere usati presso {userId} in URI. 
  
Le operazioni REST sono incluse nella tabella seguente.
  
|**Operazione**|**Descrizione**|
|:-----|:-----|
|[Ottenere gli utenti](get-users.md) <br/> |Restituisce un elenco di utenti nel repository.  <br/> |
|[Ottenere l'utente](get-user.md) <br/> |Restituisce un record utente.  <br/> |
   

