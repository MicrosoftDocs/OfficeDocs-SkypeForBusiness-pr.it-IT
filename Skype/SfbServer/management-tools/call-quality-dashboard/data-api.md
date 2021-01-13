---
title: API dei dati per Call Quality Dashboard (CQD) in Skype for Business Server
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
description: "Riepilogo: informazioni sull'API dei dati per il dashboard per la qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 367aa1bf1103863fff37fbcd4f8d9fa379de7c1d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832696"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API dei dati per Call Quality Dashboard (CQD) in Skype for Business Server
 
**Riepilogo:** Informazioni sull'API dei dati per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'API Data fornisce l'accesso programmatico per il dashboard qualità chiamata per Skype for Business Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>API dei dati per il dashboard qualità chiamata

L'API Data offre un'interfaccia di query al cubo QoE. L'API dei dati è un'API REST per l'utilizzo di database multidimensionali che fornisce metriche QoE aggregate in base alle dimensioni e ai filtri specificati.
  
Le operazioni REST sono incluse nella tabella seguente.
  

|**Operazione**|**Descrizione**|
|:-----|:-----|
|[Get Cube](get-cube.md) <br/> |Ottenere l'elenco delle dimensioni e delle misure disponibili.  <br/> |
|[Get Dimension Members](get-dimension-members.md) <br/> |Get Dimension members Operation restituisce l'elenco dei membri di una dimensione specifica. È inoltre possibile filtrare l'elenco dei membri e ottenere un sottoinsieme, per ridurre il costo di trasferimento dei cavi.  <br/> |
|[Run Query](run-query.md) <br/> |L'operazione Esegui query consente di eseguire una query sul cubo in base alle dimensioni, alle misure e ai filtri specificati e di restituire i dati.  <br/> |
|[Clear Cache](clear-cache.md) <br/> |Cancella operazione cache Elimina la cache sul server per le query e i dati. In questo modo verrà ripristinata la cache e verranno riportati i dati da un cubo QoE dopo per nuove richieste.  <br/> |
|[Get Integration Log](get-integration-log.md) <br/> |Get Integration log Operation restituisce un elenco di voci di registro che descrivono le attività nell'elaborazione del cubo QoE.  <br/> |
|[Get Last Integration Data](get-last-integration-data.md) <br/> |Recuperare i dati dell'ultima integrazione dal cubo.  <br/> |
   
 **Supporto per la condivisione delle risorse di CORS (Cross-Origin Resource) per API dei dati**
  
API dei dati supporta la condivisione delle risorse tra origini (CORS). CORS è una funzionalità HTTP che consente a un'applicazione Web in esecuzione in un dominio di accedere alle risorse in un altro dominio. I Web browser implementano una restrizione di sicurezza nota come criterio di origine dello stesso [criterio](https://www.w3.org/Security/wiki/Same_Origin_Policy) di origine che impedisce la chiamata delle API in un dominio diverso da una pagina Web. CORS fornisce un modo sicuro per consentire a un dominio (il dominio di origine) di chiamare API in un altro dominio. Per informazioni dettagliate su CORS, vedere la [specifica di CORS](https://www.w3.org/TR/cors/) .
  
 **Abilitazione di CORS per API dei dati**
  
 Di seguito è riportato un Estratto di data API web.config, che mostra due domini elencati nelle impostazioni delle applicazioni di corsTrustedOrigin. Tutte le richieste eseguite dagli script caricati da questi server sono considerate attendibili dall'API dei dati.
  
Tenere presente che il protocollo, il nome host e la porta (se presenti) sono esatte. Non inserire alcun carattere barra (/) alla fine. È possibile specificare più voci separando le virgole.
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


