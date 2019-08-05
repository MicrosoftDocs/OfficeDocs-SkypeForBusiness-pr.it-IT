---
title: Ottenere il log di integrazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: "Riepilogo: informazioni sull'operazione Get Integration log, che fa parte dell'API dati per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 58be983ff3b282c94a4b42619a6c37c6270afcb5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186944"
---
# <a name="get-integration-log"></a>Ottenere il log di integrazione
 
**Riepilogo:** Informazioni sull'operazione Get Integration log, che fa parte dell'API dati per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Integration log fa parte dell'API Data per il dashboard qualità chiamata
  
## <a name="get-integration-log"></a>Ottenere il log di integrazione

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


