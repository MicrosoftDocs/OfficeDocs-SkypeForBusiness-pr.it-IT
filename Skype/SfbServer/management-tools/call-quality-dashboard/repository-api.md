---
title: API repository per call quality dashboard (CQD) in Skype for Business Server
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
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: "Riepilogo: informazioni sull'API repository per il dashboard qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 21765c4766e7fc729988f2b8ba23241175a96584
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759698"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>API repository per call quality dashboard (CQD) in Skype for Business Server
 
**Riepilogo:** Informazioni sull'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'API repository fornisce l'accesso a livello di programmazione per call quality dashboard per Skype for Business Server.
  
## <a name="repository-api-for-call-quality-dashboard"></a>API di repository per il dashboard qualità delle chiamate

L'API repository offre un'interfaccia di accesso ai dati al database repository. Il repository consente di organizzare il contenuto in una struttura ad albero o in un grafico in modo che gli utenti possano raggrupparli nel modo più sensato per gli utenti. L'archivio supporta due tipi generali di utenti: l'utente di sistema, che è un utente predefinito che rappresenta il repository, e gli utenti normali che rappresentano gli utenti autorizzati del repository.
  
L'API di repository è costituita da tre servizi generali: 
  
- [Servizio utente per CQD-](user-service.md) per l'accesso agli utenti.
    
- [Item Service for Call Quality Dashboard (CQD)](item-service.md) - Per accedere agli elementi e ai contenuti archiviati in Elementi.
    
- [User Impostazioni Service for Call Quality Dashboard (CQD)](user-settings-service.md) - per accedere a User Impostazioni.
    
Call Quality Dashboard usa l'API repository per gestire le informazioni seguenti: 
  
- **Utente** - Rappresentazione degli utenti che hanno accesso al repository.
    
- **Report** : contiene un elenco di query, archiviate come contenuto negli elementi del repository.
    
- **Query** : usata per recuperare i dati dall'API dei dati, archiviati come contenuto negli elementi del repository.
    
- **Impostazione utente** : descrive un comportamento facoltativo dell'applicazione per l'utente.
    
  **Supporto cors (Cross-Origin Resource Sharing) per l'API repository**
  
L'API repository supporta cors (Cross-Origin Resource Sharing). CORS è una funzionalità HTTP che consente a un'applicazione Web in esecuzione in un dominio di accedere alle risorse in un altro dominio. I Web browser implementano [](https://www.w3.org/Security/wiki/Same_Origin_Policy) una restrizione di sicurezza nota come criterio di stessa origine che impedisce a una pagina Web di chiamare API in un dominio diverso. CORS offre un modo sicuro per consentire a un dominio (il dominio di origine) di chiamare le API in un altro dominio. Per informazioni [dettagliate su CORS,](https://www.w3.org/TR/cors/) vedere la specifica CORS.
  
 **Abilitazione di CORS per l'API repository**
  
 Di seguito è riportato un estratto di Repository API web.config, che mostra due domini elencati nelle impostazioni dell'applicazione corsTrustedOrigin. Tutte le richieste effettuate dagli script caricati da questi server sono attendibili dall'API repository.
  
Ricordarsi di includere il protocollo esatto, il nome host e la porta (se presente). Non inserire alcun carattere barra (/) alla fine. È possibile specificare più voci separando con virgole.
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


