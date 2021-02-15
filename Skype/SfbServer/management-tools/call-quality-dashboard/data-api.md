---
title: API dati per Call Quality Dashboard (CQD) in Skype for Business Server
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
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: "Riepilogo: informazioni sull'API dati per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 367aa1bf1103863fff37fbcd4f8d9fa379de7c1d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832696"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API dati per Call Quality Dashboard (CQD) in Skype for Business Server
 
**Riepilogo:** Informazioni sull'API dei dati per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'API dei dati fornisce l'accesso programmatico per call quality dashboard per Skype for Business Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>API dati per call quality dashboard

L'API dei dati offre un'interfaccia di query per il cubo QoE. L'API dei dati è un'API REST per l'utilizzo di database multidimensionali che fornisce metriche QoE aggregate in base a dimensioni e filtri specificati.
  
Le operazioni REST sono incluse nella tabella seguente.
  

|**Operazione**|**Descrizione**|
|:-----|:-----|
|[Get Cube](get-cube.md) <br/> |Ottenere l'elenco delle dimensioni e delle misure disponibili.  <br/> |
|[Get Dimension Members](get-dimension-members.md) <br/> |L'operazione Get Dimension Members restituisce l'elenco dei membri di una dimensione specifica. Consente inoltre di filtrare l'elenco dei membri e ottenere un sottoinsieme, per ridurre il costo del trasferimento bancario.  <br/> |
|[Run Query](run-query.md) <br/> |L'operazione Esegui query consente di eseguire una query sul cubo in base a dimensioni, misure e filtri specificati e di restituire i dati.  <br/> |
|[Clear Cache](clear-cache.md) <br/> |L'operazione Cancella cache elimina la cache sul server per query e dati. In questo modo verrà reimpostata la cache e in seguito si otterrà nuovi dati dal cubo QoE per le nuove richieste.  <br/> |
|[Get Integration Log](get-integration-log.md) <br/> |L'operazione Get Integration Log restituisce un elenco di voci di registro che descrivono le attività nell'elaborazione del cubo QoE.  <br/> |
|[Get Last Integration Data](get-last-integration-data.md) <br/> |Recuperare gli ultimi dati di integrazione dal cubo.  <br/> |
   
 **Supporto cors (Cross-Origin Resource Sharing) per l'API dei dati**
  
L'API dei dati supporta cors (Cross-Origin Resource Sharing). CORS è una funzionalità HTTP che consente a un'applicazione Web in esecuzione in un dominio di accedere alle risorse in un altro dominio. I Web browser implementano [](https://www.w3.org/Security/wiki/Same_Origin_Policy) una restrizione di sicurezza nota come criterio di stessa origine che impedisce a una pagina Web di chiamare API in un dominio diverso. CORS offre un modo sicuro per consentire a un dominio (il dominio di origine) di chiamare le API in un altro dominio. Per informazioni [dettagliate](https://www.w3.org/TR/cors/) su CORS, vedere la specifica CORS.
  
 **Abilitazione di CORS per l'API dei dati**
  
 Di seguito è riportato un estratto di Data API web.config, che mostra due domini elencati nelle impostazioni dell'applicazione corsTrustedOrigin. Tutte le richieste effettuate dagli script caricati da questi server sono attendibili dall'API dei dati.
  
Ricordarsi di includere il protocollo esatto, il nome host e la porta (se presenti). Non inserire alcun carattere barra (/) alla fine. È possibile specificare più voci separandole con una virgola.
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


