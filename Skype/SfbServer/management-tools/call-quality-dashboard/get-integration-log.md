---
title: Get Integration Log
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Riepilogo: informazioni sull''operazione Get Integration Log, che fa parte dell''API dei dati per il dashboard di qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server.'
---

# <a name="get-integration-log"></a>Get Integration Log
 
**Riepilogo:** Informazioni sull'operazione Get Integration Log, che fa parte dell'API dei dati per il dashboard di qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Integration Log fa parte dell'API dei dati per il dashboard qualità delle chiamate
  
## <a name="get-integration-log"></a>Get Integration Log

L'operazione Get Integration Log restituisce un elenco di voci di registro che descrivono le attività nell'elaborazione del cubo QoE.
  
Questa operazione è disabilitata per impostazione predefinita per motivi di sicurezza. Se disabilitata, restituisce una stringa vuota. Per abilitare questa operazione, gli amministratori devono configurare il web.config per l'applicazione Web host dell'API dati.
  

|Metodo|**URI richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |\<portal\>https:///QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** - Nessuno.
  
 **Intestazioni richiesta** - Nessuna intestazione aggiuntiva.
  
 **Corpo della richiesta** - Nessuno.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).
  
 **Intestazioni di risposta** - Nessuna intestazione aggiuntiva.
  
 **Corpo risposta** : di seguito è riportata una struttura di esempio di voci di registro.
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


