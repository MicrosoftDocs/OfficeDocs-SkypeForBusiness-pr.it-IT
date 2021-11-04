---
title: API dati per call quality dashboard (CQD) in Skype for Business Server
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
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: "Riepilogo: informazioni sull'API dei dati per il dashboard di qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 3a305ce3c6b4a1bbfcc0fbdedbb575477f76d62c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60742042"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API dati per call quality dashboard (CQD) in Skype for Business Server
 
**Riepilogo:** Informazioni sull'API dei dati per il dashboard di qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'API dei dati fornisce l'accesso a livello di codice per call quality dashboard per Skype for Business Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>API dei dati per il dashboard qualità delle chiamate

L'API dei dati offre un'interfaccia di query per il cubo QoE. L'API dei dati è un'API REST per l'utilizzo di database multidimensionali che fornisce metriche QoE aggregate in base a dimensioni e filtri specificati.
  
Le operazioni REST sono incluse nella tabella seguente.
  

|**Operazione**|**Descrizione**|
|:-----|:-----|
|[Get Cube](get-cube.md) <br/> |Ottenere l'elenco delle dimensioni e delle misurazioni disponibili.  <br/> |
|[Get Dimension Members](get-dimension-members.md) <br/> |L'operazione Get Dimension Members restituisce l'elenco dei membri di una dimensione specifica. Offre anche la possibilità di filtrare l'elenco dei membri e ottenere un sottoinsieme, per ridurre il costo di trasferimento dei fili.  <br/> |
|[Run Query](run-query.md) <br/> |L'operazione Esegui query consente di eseguire una query sul cubo in base a dimensioni, misure e filtri specificati e di restituire i dati.  <br/> |
|[Clear Cache](clear-cache.md) <br/> |L'operazione Cancella cache elimina la cache sul server per query e dati. In questo modo verrà reimpostata la cache e verranno successivamente ripristinati i dati dal cubo QoE per le nuove richieste.  <br/> |
|[Get Integration Log](get-integration-log.md) <br/> |L'operazione Get Integration Log restituisce un elenco di voci di registro che descrivono le attività nell'elaborazione del cubo QoE.  <br/> |
|[Get Last Integration Data](get-last-integration-data.md) <br/> |Recuperare gli ultimi dati di integrazione dal cubo.  <br/> |
   
 **Supporto cors (Cross-Origin Resource Sharing) per l'API dei dati**
  
L'API dei dati supporta cors (Cross-Origin Resource Sharing). CORS è una funzionalità HTTP che consente a un'applicazione Web in esecuzione in un dominio di accedere alle risorse in un altro dominio. I Web browser implementano [](https://www.w3.org/Security/wiki/Same_Origin_Policy) una restrizione di sicurezza nota come criterio di stessa origine che impedisce a una pagina Web di chiamare API in un dominio diverso. CORS offre un modo sicuro per consentire a un dominio (il dominio di origine) di chiamare le API in un altro dominio. Per informazioni [dettagliate su CORS,](https://www.w3.org/TR/cors/) vedere la specifica CORS.
  
 **Abilitazione di CORS per l'API dei dati**
  
 Di seguito è riportato un estratto di Data API web.config, che mostra due domini elencati nelle impostazioni dell'applicazione corsTrustedOrigin. Tutte le richieste effettuate dagli script caricati da questi server sono attendibili dall'API dei dati.
  
Ricordarsi di includere il protocollo esatto, il nome host e la porta (se presente). Non inserire alcun carattere barra (/) alla fine. È possibile specificare più voci separando con virgole.
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


