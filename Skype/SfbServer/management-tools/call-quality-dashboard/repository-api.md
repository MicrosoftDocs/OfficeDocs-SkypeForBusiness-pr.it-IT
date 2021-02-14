---
title: Repository API for Call Quality Dashboard (CQD) in Skype for Business Server
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
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: "Riepilogo: informazioni sull'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 982ec0932f0a57958e1929a6ae2413ada0b5c9fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803126"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>Repository API for Call Quality Dashboard (CQD) in Skype for Business Server
 
**Riepilogo:** Informazioni sull'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'API repository fornisce l'accesso programmatico per call quality dashboard per Skype for Business Server.
  
## <a name="repository-api-for-call-quality-dashboard"></a>API di repository per call quality dashboard

L'API repository offre un'interfaccia di accesso ai dati per il database repository. Il repository consente di organizzare il contenuto in una struttura ad albero o in un grafico in modo che gli utenti possano raggrupparli nel modo più opportuno per gli utenti. L'archivio supporta due tipi generali di utenti: utente di sistema, ovvero un utente predefinito che rappresenta il repository, e utenti normali che rappresentano gli utenti autorizzati del repository.
  
L'API repository è costituita da tre servizi generali: 
  
- [Servizio utente per CQD-](user-service.md) per l'accesso agli utenti.
    
- [Item Service for Call Quality Dashboard (CQD)](item-service.md) - Per accedere agli elementi e ai contenuti archiviati in Elementi.
    
- [Servizio impostazioni utente per call quality dashboard (CQD)](user-settings-service.md) - per l'accesso alle impostazioni utente.
    
Call Quality Dashboard usa l'API Repository per gestire le informazioni seguenti: 
  
- **User:** rappresentazione degli utenti che hanno accesso al repository.
    
- **Report:** contiene un elenco di query, archiviate come contenuto negli elementi del repository.
    
- **Query:** usata per recuperare i dati dall'API dei dati, archiviati come contenuto negli elementi del repository.
    
- **Impostazione utente:** descrive un comportamento facoltativo dell'applicazione per l'utente.
    
  **Supporto cors (Cross-Origin Resource Sharing) per l'API repository**
  
L'API repository supporta cors (Cross-Origin Resource Sharing). CORS è una funzionalità HTTP che consente a un'applicazione Web in esecuzione in un dominio di accedere alle risorse in un altro dominio. I Web browser implementano [](https://www.w3.org/Security/wiki/Same_Origin_Policy) una restrizione di sicurezza nota come criterio di stessa origine che impedisce a una pagina Web di chiamare API in un dominio diverso. CORS offre un modo sicuro per consentire a un dominio (il dominio di origine) di chiamare le API in un altro dominio. Per informazioni [dettagliate](https://www.w3.org/TR/cors/) su CORS, vedere la specifica CORS.
  
 **Abilitazione dell'API CORS per repository**
  
 Di seguito è riportato un estratto di Repository API web.config, che mostra due domini elencati nelle impostazioni dell'applicazione corsTrustedOrigin. Tutte le richieste effettuate dagli script caricati da questi server sono attendibili dall'API repository.
  
Ricordarsi di includere il protocollo esatto, il nome host e la porta (se presenti). Non inserire alcun carattere barra (/) alla fine. È possibile specificare più voci separandole con una virgola.
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


