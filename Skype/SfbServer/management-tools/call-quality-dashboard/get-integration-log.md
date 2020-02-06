---
title: Get Integration Log
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: "Riepilogo: informazioni sull'operazione Get Integration log, che fa parte dell'API dati per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 9caa909e80a0bab5257af16fe77e9d154947a56e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816815"
---
# <a name="get-integration-log"></a>Get Integration Log
 
**Riepilogo:** Informazioni sull'operazione Get Integration log, che fa parte dell'API dati per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Integration log fa parte dell'API Data per il dashboard qualità chiamata
  
## <a name="get-integration-log"></a>Get Integration Log

Get Integration log Operation restituisce un elenco delle voci di log che descrivono le attività nell'elaborazione dei cubi QoE.
  
Questa operazione è disabilitata per impostazione predefinita per motivi di sicurezza. Quando disabilitata, restituisce una stringa vuota. Per abilitare questa operazione, gli amministratori devono configurare l'applicazione Web host Web. config per l'API dati.
  

|Metodo|**URI di richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|Ottieni  <br/> |/QoEDataService/IntegrationLog\<portale\>https://  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** -None.
  
 **Richiedi intestazioni** -nessuna intestazione aggiuntiva.
  
 **Richiedi corpo** -nessuno.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).
  
 **Intestazioni di risposta** -nessuna intestazione aggiuntiva.
  
 **Corpo risposta** : di seguito è riportata una struttura di esempio delle voci di log.
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


