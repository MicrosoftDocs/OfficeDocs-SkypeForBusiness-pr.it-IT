---
title: API dati per Call Quality Dashboard (Call Quality Dashboard) in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: "Riepilogo: informazioni sull'API dati per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 016cc1be9f5cd5506f8ee7d8ddbe2765e0015ffd
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "36571920"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API dati per Call Quality Dashboard (Call Quality Dashboard) in Skype for Business Server
 
**Riepilogo:** Informazioni sull'API dati per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'API dati offre accesso a livello di codice per Call Quality dashboard per Skype for Business Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>API dati per dashboard qualità chiamata

L'API dati offre un'interfaccia di query al cubo QoE. L'API dati è un'API REST per l'uso di database multidimensionali che fornisce metriche QoE aggregate basate su dimensioni e filtri specificati.
  
Le operazioni REST sono incluse nella tabella seguente.
  

|**Operazione**|**Descrizione**|
|:-----|:-----|
|[Ottieni cubo](get-cube.md) <br/> |Ottenere l'elenco delle dimensioni e delle misure disponibili.  <br/> |
|[Ottenere i membri della dimensione](get-dimension-members.md) <br/> |L'operazione get Members Dimension restituisce l'elenco dei membri di una dimensione specifica. È anche possibile filtrare l'elenco dei membri e ottenere un sottoinsieme, per ridurre il costo del bonifico bancario.  <br/> |
|[Esegui query](run-query.md) <br/> |L'operazione Esegui query offre la possibilità di eseguire una query sul cubo in base a dimensioni, misure e filtri specificati e restituire i dati.  <br/> |
|[Cancellare la cache](clear-cache.md) <br/> |Cancella operazione cache Elimina la cache sul server per query e dati. In questo modo verrà reimpostata la cache e in seguito verranno riprodotti nuovi dati dal cubo QoE per le nuove richieste.  <br/> |
|[Ottenere il log di integrazione](get-integration-log.md) <br/> |Get Integration log Operation restituisce un elenco delle voci di log che descrivono le attività nell'elaborazione dei cubi QoE.  <br/> |
|[Ottenere gli ultimi dati di integrazione](get-last-integration-data.md) <br/> |Ottenere gli ultimi dati di integrazione dal cubo.  <br/> |
   
 **Supporto CORS (Cross-Origin Resource Sharing) per API dati**
  
L'API dei dati supporta la condivisione delle risorse CORS (Cross-Origin Resource Sharing). CORS è una caratteristica HTTP che consente a un'applicazione Web in uso in un dominio di accedere alle risorse in un altro dominio. I Web browser implementano una restrizione di sicurezza nota come criterio di origine [della stessa origine](https://www.w3.org/Security/wiki/Same_Origin_Policy) che impedisce la chiamata delle API in un dominio diverso da una pagina Web. CORS offre un modo sicuro per consentire a un dominio (il dominio di origine) di chiamare le API in un altro dominio. Vedere la [specifica CORS](https://www.w3.org/TR/cors/) per informazioni dettagliate su CORS.
  
 **Abilitazione di CORS for Data API**
  
 Di seguito è riportato un Estratto di data API Web. config, che mostra due domini elencati nelle impostazioni delle applicazioni di corsTrustedOrigin. Tutte le richieste effettuate dagli script caricati da questi server sono attendibili dall'API dati.
  
Ricordarsi di includere l'esatto protocollo, il nome host e la porta (se presenti). Non inserire alcun carattere barra (/) alla fine. È possibile specificare più voci separandoli con una virgola.
  
```
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


