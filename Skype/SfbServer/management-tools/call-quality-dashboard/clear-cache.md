---
title: Clear Cache
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Riepilogo: informazioni sull''operazione Cancella cache, che fa parte dell''API dati per il dashboard di qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server.'
---

# <a name="clear-cache"></a>Clear Cache
 
**Riepilogo:** Informazioni sull'operazione Cancella cache, che fa parte dell'API dati per il dashboard qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'operazione Cancella cache fa parte dell'API dati per il dashboard qualità delle chiamate.
  
## <a name="clear-cache"></a>Clear Cache

L'operazione Cancella cache elimina la cache sul server per query e dati. In questo modo verrà reimpostata la cache e verranno successivamente ripristinati i dati dal cubo QoE per le nuove richieste.
  

|**Metodo**|**URI richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|POST  <br/> |\<portal\>https:///QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** - Nessuno.
  
 **Intestazioni richiesta** - Nessuna intestazione aggiuntiva.
  
 **Corpo della richiesta** - Nessuno.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).
  
 **Intestazioni di risposta** - Nessuna intestazione aggiuntiva.
  
 **Corpo risposta** - Nessuno.
  

