---
title: Clear Cache
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
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: "Riepilogo: informazioni sull'operazione Clear cache, che fa parte dell'API dei dati per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: c9b966bb1e35a5a6255cd75ea6c685daaf220a09
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806416"
---
# <a name="clear-cache"></a>Clear Cache
 
**Riepilogo:** Informazioni sull'operazione Clear cache, che fa parte dell'API Data per il dashboard per la qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Clear cache è parte dell'API Data per il dashboard qualità chiamata.
  
## <a name="clear-cache"></a>Clear Cache

Cancella operazione cache Elimina la cache sul server per le query e i dati. In questo modo verrà ripristinata la cache e verranno riportati i dati da un cubo QoE dopo per nuove richieste.
  

|**Metodo**|**URI della richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** -None.
  
 **Intestazioni richieste** -nessuna intestazione aggiuntiva.
  
 **Corpo richiesta** -nessuno.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** -un'operazione completata restituisce il codice di stato 200 (OK).
  
 **Intestazioni di risposta** -Nessun intestazioni aggiuntive.
  
 **Corpo di risposta** -nessuno.
  

