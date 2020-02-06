---
title: Clear Cache
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
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: "Riepilogo: informazioni sull'operazione Clear cache, che fa parte dell'API dati per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 821b02f204c98f5acefe69df1c848c31cd2205b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816885"
---
# <a name="clear-cache"></a>Clear Cache
 
**Riepilogo:** Informazioni sull'operazione Clear cache, che fa parte dell'API dati per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Cancella cache fa parte dell'API dati per il dashboard della qualità delle chiamate.
  
## <a name="clear-cache"></a>Clear Cache

Cancella operazione cache Elimina la cache sul server per query e dati. In questo modo verrà reimpostata la cache e in seguito verranno riprodotti nuovi dati dal cubo QoE per le nuove richieste.
  

|**Metodo**|**URI di richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|Inserisci  <br/> |/QoEDataService/ClearCache\<portale\>https://  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** -None.
  
 **Richiedi intestazioni** -nessuna intestazione aggiuntiva.
  
 **Richiedi corpo** -nessuno.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).
  
 **Intestazioni di risposta** -nessuna intestazione aggiuntiva.
  
 **Corpo della risposta** -nessuno.
  

