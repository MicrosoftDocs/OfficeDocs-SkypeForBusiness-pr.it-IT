---
title: API dati per Call Quality Dashboard (CQD) in Skype for Business Server
ms.reviewer: ''
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
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: "Riepilogo: informazioni sull'API Dati per Call Quality Dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 3204398dcf667f785f1efe71cc4d6dc5478ce54d
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675738"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API dati per Call Quality Dashboard (CQD) in Skype for Business Server
 
**Riepilogo:** Informazioni sull'API Dati per Call Quality Dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'API Dati fornisce l'accesso a livello di codice per call quality dashboard per Skype for Business Server.
  
## <a name="data-api-for-call-quality-dashboard"></a>API dati per call quality dashboard

L'API Dati offre un'interfaccia di query al cubo QoE. L'API Dati è un'API REST per l'uso di database multidimensionali che fornisce metriche QoE aggregate in base a dimensioni e filtri specificati.
  
Le operazioni REST sono incluse nella tabella seguente.
  

|**Operazione**|**Descrizione**|
|:-----|:-----|
|[Get Cube](get-cube.md) <br/> |Ottenere l'elenco delle dimensioni e delle misure disponibili.  <br/> |
|[Get Dimension Members](get-dimension-members.md) <br/> |L'operazione Get Dimension Members restituisce l'elenco dei membri di una dimensione specifica. Offre anche la possibilità di filtrare l'elenco di membri e ottenere un subset, per ridurre il costo del trasferimento in rete.  <br/> |
|[Run Query](run-query.md) <br/> |L'operazione Esegui query consente di eseguire una query sul cubo in base alle dimensioni, alle misure e ai filtri specificati e di restituire i dati.  <br/> |
|[Clear Cache](clear-cache.md) <br/> |L'operazione Cancella cache elimina la cache nel server per le query e i dati. In questo modo la cache verrà reimpostata e in seguito verranno ottenuti nuovi dati da QoE Cube per le nuove richieste.  <br/> |
|[Get Integration Log](get-integration-log.md) <br/> |L'operazione Get Integration Log restituisce un elenco di voci di log che descrivono le attività nell'elaborazione del cubo QoE.  <br/> |
|[Get Last Integration Data](get-last-integration-data.md) <br/> |Ottenere gli ultimi dati di integrazione dal cubo.  <br/> |
   
 **Supporto cors (Cross-Origin Resource Sharing) per l'API dati**
  
L'API dati supporta la condivisione delle risorse tra origini (CORS). CORS è una funzionalità HTTP che consente a un'applicazione Web in esecuzione in un dominio di accedere alle risorse in un altro dominio. I Web browser implementano una restrizione di sicurezza nota come criteri [di](https://www.w3.org/Security/wiki/Same_Origin_Policy) stessa origine che impedisce a una pagina Web di chiamare LE API in un dominio diverso. CORS offre un modo sicuro per consentire a un dominio (il dominio di origine) di chiamare le API in un altro dominio. Per informazioni dettagliate su CORS, vedere la [specifica CORS](https://www.w3.org/TR/cors/) .
  
 **Abilitazione di CORS per l'API dati**
  
 Di seguito è riportato un estratto della web.config dell'API Dati, che mostra due domini elencati nelle impostazioni dell'applicazione corsTrustedOrigin. Tutte le richieste effettuate dagli script caricati da questi server sono considerate attendibili dall'API dati.
  
Ricordarsi di includere il protocollo esatto, il nome host e la porta (se presente). Non inserire alcun carattere barra in avanti (/) alla fine. È possibile specificare più voci separando con virgole.
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
...  </appSettings>
</configuration>
```


